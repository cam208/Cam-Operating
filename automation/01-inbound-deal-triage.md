# Workflow 1 — Inbound Deal Triage (Auto Loop)

Turns the existing manual triage into a standing loop: a deal lands, Olli reads
everything, runs the triage skill, logs it, and hands Cam a decision-ready summary — with
the investment decision itself always left to Cam.

> Builds directly on [`../skills/deal-triage/SKILL.md`](../skills/deal-triage/SKILL.md).
> That skill is the *how*; this spec is the *when, from where, and how autonomously*.

## Purpose

Compress the time from "a deal arrives" to "Cam has a triage PDF, a pipeline entry, and a
recommendation" from days to minutes, without lowering the diligence bar — every triage
still runs the full 7-stage-aligned process, scorecard, EV model, and market stress test.

## Trigger

Any of:
- An email to `cam@` / `olli@` that looks like a deal (deck attached, "raising," intro
  from a known channel — RBCx list, SVG/THRIVE, warm operator intro).
- Cam forwards a deal to `olli@redstickvc.com` (explicit trigger — highest priority).
- A complete package lands in the watched Drive folder via Workflow 2 (intake) with the
  `deal` classification.

**SLA:** triage a *complete* package within **48h** of it landing (per
[`../Redstick-Knowledge-Base/02-deal-sourcing-pipeline/02-pipeline-crm-ops.md`](../Redstick-Knowledge-Base/02-deal-sourcing-pipeline/02-pipeline-crm-ops.md)).

## Inputs

| Source | What Olli pulls |
|---|---|
| Gmail thread | Body, sender, intro context, all attachments |
| Drive | Deck, cap table, data-room files linked or attached |
| Otter | Any founder-call transcript already recorded |
| Web | The five mandatory market-stress searches |

## Pipeline

1. **Detect & de-dupe.** Identify the company. Search the Notion pipeline
   (`77829e04-…`) by name — if it exists, this is an *update*, not a new entry.
2. **Gather all docs.** Read every attachment and linked file. If a file can't be read,
   record the gap and proceed (flagging it), or ask Cam/founder to re-share.
3. **Classify diligence stage** (Deck / Light Data Room / … / Full DD).
4. **Run the triage skill end to end** — snapshot, on-thesis fit, deal structure,
   five-lens scorecard, MOIC EV model ($100K & $250K), market stress test, conviction
   gaps, recommendation. All hard rules apply (no $500K/$1M, no ownership gate, MOIC not
   IRR, bear floor ≥20%, cite every figure).
5. **Produce the triage PDF** (Redstick green, Fund I header) → Drive archive folder.
6. **Log to Notion** — create or update the pipeline row with all fields (decision,
   score, EV, thesis tag, strategic-LP fit, concentration, round timing, source…). Paste
   the Drive link into `Triage Doc`.
7. **Draft the message to Cam** — 5–7 sentences as Olli: what it is, the strongest signal,
   the decisive reason, what's missing, recommendation at Redstick's terms. Saved as a
   Gmail draft (not sent).
8. **If ADVANCE and Cam approves** → offer to draft the founder intro-call email and
   propose calendar slots (Workflow-adjacent; still Cam-sent).

## Outputs

- `${Company}-Triage.pdf` in the Drive triage archive
- A created/updated **Notion pipeline entry**
- A **Gmail draft** to Cam with the recommendation
- A one-line note in the next **Weekly Operating Brief**

## Human-in-the-loop

- Olli **recommends** ADVANCE / WATCH / PASS — Cam **decides**.
- The message to Cam is a **draft**; nothing goes to the founder until Cam sends it.
- On a PASS, Olli does **not** auto-reply to the founder — it drafts a kind decline for
  Cam's review.

## Guardrails

- Every financial figure cites its source; inferences `[Assumed]`; call data `[to confirm
  on call]`.
- **Never** model $500K/$1M or use the founder's ask. **Never** pass on ownership/round-size.
- If the deck implies a fund size/check that contradicts `../CLAUDE.md`, **flag it** in
  the message to Cam rather than adopting it.
- Search Notion before creating — **never duplicate** a pipeline row.

## Failure modes & fallbacks

| Failure | Fallback |
|---|---|
| Attachment unreadable / permission denied | Flag the gap, triage what's available, ask for re-share |
| Company already in pipeline | Update the existing row; note what changed since last triage |
| Prior SAFEs / missing cap table | Mark EV `[provisional — cap table required]`; add to conviction gaps |
| Market-stress searches inconclusive | Report the uncertainty; do not fabricate a verdict |
| Off-thesis | Short-circuit to a quick PASS draft; skip the full EV model |

## Build plan

- **Crawl (now):** Cam forwards a deal → Olli runs the skill on demand → produces all four
  outputs. *(Largely working today.)*
- **Walk:** Olli watches the inbox, detects deal-shaped mail, and auto-runs triage on
  complete packages, surfacing a draft to Cam. Cam reviews a queue.
- **Run:** Full loop with Workflow 2 feeding it, auto-scheduling proposed intro calls on
  ADVANCE (Cam one-click approves), and pipeline hygiene (stale-deal nudges) automated.

## Open questions

- Confidence threshold for "auto-run vs ask first" on ambiguous inbound. `[confirm with Cam]`
- Should WATCH deals get an automatic re-trigger when the flip condition's data arrives? `[confirm]`
