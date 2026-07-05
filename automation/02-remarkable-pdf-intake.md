# Workflow 2 — Remarkable & PDF Intake (Classify & Route)

The front door for anything that arrives as a PDF. Cam's reMarkable tablet exports
handwritten notes and marked-up decks to a watched Drive folder; decks, data-room files,
and scanned documents also land there. Olli reads each one — including handwriting via
vision/OCR — figures out *what it is*, and routes it to the workflow that should own it.

> This is the intake layer that feeds [Inbound Deal Triage](./01-inbound-deal-triage.md)
> and [Portfolio Report Intake](./03-portfolio-report-intake.md). It classifies and routes;
> it does **not** make investment decisions or send anything outward.

## Purpose

Make sure nothing Cam captures on paper or drops in Drive falls through the cracks. Every
PDF gets read, transcribed if handwritten, classified against a fixed taxonomy, filed to a
predictable location, and — where it belongs to another workflow — handed off with a clean
payload. Cam should be able to scribble a meeting note on the reMarkable, walk away, and
find it transcribed, filed, and cross-referenced to the right deal without lifting a finger.

## Trigger

Any of:
- A **new file appears in the watched Drive intake folder** (e.g. `/Redstick/Intake/`) —
  reMarkable exports land here automatically; Cam or Shane can also drop files in.
- Cam **forwards a PDF** to `olli@redstickvc.com` (explicit trigger — highest priority).
- A file is moved into the intake folder from elsewhere in Drive.

Detection is **poll-or-event**: a Drive change-watch webhook if available, otherwise a
poll every ~10 min. De-dupe on Drive file ID so a re-synced reMarkable export is not
processed twice.

## Inputs

| Source | What Olli pulls |
|---|---|
| Google Drive | The PDF itself, filename, folder, created/modified time, owner |
| Vision / OCR | Rendered page images → transcribed text (typed **and** handwritten) |
| Notion | Deal Pipeline (`77829e04-…`) + Portfolio Snapshot, to match a company/meeting |
| Otter.ai | Call transcripts to cross-reference against handwritten meeting notes |
| Limitless | Ambient capture to confirm *which* meeting a note belongs to |
| Gmail | If forwarded, the covering message and any sender/context |

## Pipeline

1. **Ingest.** Pick up the new file; capture Drive ID, name, folder, timestamps. Skip if
   the file ID was already processed (idempotency log).
2. **Read.** Extract embedded text where present. For scanned/handwritten pages, render to
   images and run **vision OCR**. Track a per-page confidence score.
3. **Transcribe handwriting.** Produce a clean transcript. Anything the model cannot read
   confidently is marked **`[illegible]`** — never guessed or fabricated (provenance rule).
   If overall confidence is low, flag the whole doc for Cam's eyes.
4. **Classify.** Assign exactly one class from the taxonomy below, with a confidence score
   and a one-line rationale. If confidence is below threshold, route to **Ask Cam**.
5. **Match to a company/meeting.** Search Notion (pipeline + snapshot) by name; for meeting
   notes, cross-reference Otter/Limitless by date/attendees to bind the note to the right
   meeting and deal/portfolio company.
6. **File.** Move/copy the PDF to its canonical Drive location (see Outputs) and record a
   Notion note/entry with the transcript, classification, confidence, and source link.
7. **Route.** Hand off to the owning workflow with a structured payload, or file-only for
   classes that need no downstream action.
8. **Log** a one-line entry for the next
   [Weekly Operating Brief](./04-weekly-operating-brief.md) (what came in, how it was routed).

### Classification taxonomy

| Class | What it looks like | Route / action | SLA |
|---|---|---|---|
| **Deal deck / data-room doc** | Pitch deck, cap table, data-room export, teaser | Hand off to [Workflow 1 — Deal Triage](./01-inbound-deal-triage.md) with the `deal` classification | Triage within **48h** of a complete package |
| **Founder / portfolio update** | Investor update, KPI sheet, board deck from a portfolio co | Hand off to [Workflow 3 — Portfolio Report Intake](./03-portfolio-report-intake.md) | Ingest same-day; flags to Cam |
| **Handwritten meeting notes** | reMarkable notes from a founder/LP/team meeting | Transcribe → attach to the matched deal / portfolio company, or to a meeting-notes store; cross-ref Otter/Limitless transcript for the same meeting | Same-day |
| **LP / legal doc** | LPA, side letter, subscription, KYC, term sheet, counsel memo | **File + flag to Cam** (draft a short heads-up note); no auto-action | Flag same-day |
| **Personal / other** | Non-Redstick, receipts, misc scans | File to a personal/misc folder; **no action** | — |

Ambiguous or mixed documents (e.g. a deck with handwritten margin notes) are classified by
their **primary** content and the secondary content is noted — a marked-up deck routes as a
**deal** with the handwritten annotations transcribed and attached.

## Outputs

- The PDF **filed** to its canonical Drive location:
  - deal → `/Redstick/Deals/${Company}/`
  - portfolio → `/Redstick/Portfolio/${Company}/`
  - meeting notes → `/Redstick/Meeting-Notes/${YYYY-MM}/`
  - LP/legal → `/Redstick/LP-Legal/` (access-restricted)
  - personal → `/Redstick/Personal/`
- A **Notion note/entry**: transcript, classification + confidence, matched company/meeting,
  and the Drive source link.
- A **hand-off payload** to Workflow 1 or 3 (see below), when applicable.
- A one-line note in the next **Weekly Operating Brief**.

### Hand-off payload (to Workflow 1 / 3)

```
{ source_file: <drive_id>, drive_link: <url>, class: deal|portfolio,
  company: <name or null>, confidence: 0–1, transcript_or_text: <…>,
  notion_ref: <page id>, matched_meeting: <otter/limitless id or null>,
  notes: <secondary content, e.g. handwritten annotations> }
```

## Human-in-the-loop

| Step | Autonomy |
|---|---|
| Read, transcribe, OCR handwriting | ✅ Autonomous |
| Classify + file to Drive + write internal Notion note | ✅ Autonomous, logged |
| Route to Workflow 1 / 3 (internal hand-off) | ✅ Autonomous |
| **Low-confidence** classification or transcription | ⛔ Ask Cam before routing |
| LP / legal document | ⛔ File + flag; Cam decides next step |
| Any external email / reply to a founder or LP | ⛔ Draft only; Cam sends |
| Investment decision on a routed deck | ⛔ Owned by Cam via Workflow 1 |

Default posture per [`README.md`](./README.md): **Olli prepares, Cam commits.** Classifying
and routing to *internal* records is autonomous; anything outward-facing or any judgment
call on a low-confidence read stops for Cam.

## Guardrails

- **Never fabricate text it can't read.** Unreadable handwriting is `[illegible]`; low-
  confidence transcription is flagged, never smoothed over into a confident guess.
- **Provenance always.** The Notion note links back to the source PDF and page; extracted
  figures carry their source. Inferences `[Assumed]`, call-sourced data `[to confirm on call]`.
- **Fund facts are hard-coded.** If a routed deck implies a fund size or check that
  contradicts [`../CLAUDE.md`](../CLAUDE.md) ($100K/$250K, $5M fund-returner bar, MOIC),
  pass the conflict through in the hand-off — Workflow 1 flags it, intake never adopts it.
- **Currency labels.** Any dollar figure surfaced in a note is tagged `USD` or `CAD`.
- **Search before creating.** Match against the existing Notion company before creating a
  new note or entry — never duplicate a pipeline/portfolio row.
- **Privacy.** LP/legal and personal docs stay in access-restricted Redstick Drive; nothing
  leaves Redstick systems without Cam's go
  (see [`../Redstick-Knowledge-Base/07-governance-compliance/`](../Redstick-Knowledge-Base/07-governance-compliance/)).

## Failure modes & fallbacks

| Failure | Fallback |
|---|---|
| PDF unreadable / corrupt / permission denied | Log the gap, leave file in intake, flag to Cam for re-share |
| OCR confidence low across the doc | File as-is, mark transcript `[low-confidence]`, ask Cam to confirm before routing |
| Handwriting partially illegible | Transcribe what's legible; mark gaps `[illegible]`; never guess |
| Classification ambiguous / mixed content | Route to **Ask Cam** with the top-2 candidate classes and rationale |
| Company can't be matched in Notion | File to a `/Redstick/Unmatched/` holding folder; ask Cam to identify, or let Workflow 1/3 create the record |
| Duplicate export (reMarkable re-sync) | De-dupe on Drive file ID; skip silently |
| Meeting note with no matching transcript | Attach to the meeting-notes store dated; note "no Otter/Limitless match found" |

## Build plan

- **Crawl (now):** Cam forwards or drops a PDF → Olli reads it, transcribes handwriting,
  classifies, and replies with the classification + a suggested route. Cam confirms; Olli
  files and hands off. *(On-demand, human-confirmed routing.)*
- **Walk:** Olli **polls** the watched intake folder, auto-classifies and auto-files, and
  auto-routes the high-confidence **deal** and **portfolio** classes into Workflows 1/3.
  Low-confidence and LP/legal stop for Cam. Otter/Limitless cross-referencing on meeting notes.
- **Run:** Event-driven (Drive change-watch), full auto classify + file + route with a
  confidence gate, a review queue for anything below threshold, and clean idempotency so
  re-syncs and re-forwards never double-process.

## Open questions

- Confidence threshold for auto-route vs. Ask-Cam on classification and on handwriting OCR. `[confirm with Cam]`
- Canonical Drive folder structure — confirm the paths above match Cam's actual layout. `[confirm]`
- Should the meeting-notes store live in Notion, Drive, or both (transcript in Notion, PDF in Drive)? `[confirm]`
- reMarkable export format — single PDF per notebook vs. per-page; affects de-dupe and matching. `[confirm]`
- Do LP/legal docs need a separate, tighter access-control path than the general intake folder? `[confirm with Cam]`
