# Workflow 3 — Portfolio Report Intake (Auto Ingest, Human on Flags)

Turns the monthly/quarterly founder update into a standing loop: an update lands, Olli
reads it, extracts the KPIs, updates the Notion **Portfolio Snapshot** (Cam's quick-glance
view of every active company), and surfaces the flags that matter — runway risk, a down-round
signal, a churned logo, co-founder friction, an ask for help — to Cam. The internal record
updates itself; every judgment call and every word back to a founder stays with Cam.

> Builds on [`../Redstick-Knowledge-Base/05-portfolio-services/01-onboarding.md`](../Redstick-Knowledge-Base/05-portfolio-services/01-onboarding.md)
> (the monthly-update template + how the Snapshot is populated) and
> [`../Redstick-Knowledge-Base/09-playbooks/03-crisis-management.md`](../Redstick-Knowledge-Base/09-playbooks/03-crisis-management.md)
> (the crisis signals this workflow is built to detect early).

## Purpose

Make the Portfolio Snapshot always-current with zero manual data entry, and make sure a
crisis signal buried in paragraph four of a Tuesday-night email reaches Cam the same day —
not at the next quarterly sweep. Reporting is a condition of the relationship, so this
workflow also tracks *who has reported and who is overdue* and feeds that to the Weekly
Operating Brief. Speed beats perfection: a same-day flag beats a perfect memo next week.

## Trigger

Any of:
- A **founder-update email** to `olli@` / `cam@` from a known portfolio-company domain or
  sender — detected by the sender matching a Snapshot record, or subject/body matching the
  update template ("REDSTICK PORTFOLIO UPDATE", "monthly update", KPI table).
- A **founder-update PDF/attachment** routed in by [Workflow 2](./02-remarkable-pdf-intake.md)
  with the `portfolio-update` classification (dashboard export, deck, board pack).
- A **scheduled nudge**: a company's monthly update is overdue (cadence is "by the 5th" per
  onboarding). If nothing has landed, Olli drafts the one reminder; a second consecutive
  miss is escalated to Cam as a relationship signal, not an admin miss.
- A **board/update-call transcript** appears in Otter/Limitless — Olli pulls it as
  corroborating context for the written update (never as a substitute for it).

**SLA:** ingest + Snapshot update within **24h** of an update landing; **high-severity flags
surfaced to Cam the same day.**

## Inputs

| Source | What Olli pulls |
|---|---|
| Gmail thread | Update body, sender, month covered, any attached dashboard/deck |
| Google Drive | Attached or linked update files; prior updates for trend comparison |
| Notion — Portfolio Snapshot | The company's existing row + last month's figures (for deltas) |
| Notion — Deal Pipeline (`77829e04-…`) | Entry terms/cap, to cross-ref follow-on math |
| Otter / Limitless | Board/observer or update-call transcript for the same period |

## Pipeline

1. **Identify the company & de-dupe.** Match sender/domain to a Snapshot record. This is
   always an **update** to an existing row — never create a duplicate company. If no record
   matches, flag to Cam (unknown sender, or a company missing from the Snapshot).
2. **Read everything.** Email body + all attachments + any same-period call transcript. If a
   file can't be read, record the gap and proceed on what's available.
3. **Extract the KPI fields** (table below) with provenance. Pull last month's figures from
   the Snapshot to compute deltas. Label every dollar `USD` or `CAD`.
4. **Trend-integrity check.** Compare each number to prior reports. If this month's figure
   contradicts a previously reported one (e.g. last month's "cash" and this month's implied
   burn don't reconcile), flag the discrepancy — do not silently overwrite.
5. **Run flag detection** (table below) across the whole update — metrics *and* prose. Asks
   and lowlights often carry the real signal.
6. **Update the Portfolio Snapshot** — one row per company: metrics, deltas, open asks,
   reported-this-period = yes, date received. Log a missed update as a flag, never blank.
7. **Follow-on / markup check.** If the update mentions raising a new round, cross-ref the
   [markups playbook](../Redstick-Knowledge-Base/09-playbooks/02-markups.md) and flag for the
   follow-on decision framework (classify up / flat / down / bridge). Down-round language
   routes to crisis, not markups.
8. **Draft the flag brief to Cam** (only if flags fire) — what fired, severity, the source
   line, the tied playbook, and a recommended first move. High-severity always surfaces.
9. **Feed cadence status** (who reported, who's overdue) to the
   [Weekly Operating Brief](./04-weekly-operating-brief.md).

## Extraction fields

Provenance rule: every figure is quoted from the update; anything absent is **`[not reported]`**,
never inferred. Conversation/transcript-sourced figures are `[to confirm]`; inferences `[Assumed]`.

| Field | Source in the update | Notes |
|---|---|---|
| Cash in bank | Key Metrics table | Label `USD`/`CAD`; `[not reported]` if absent |
| Net monthly burn | Key Metrics table | Basis for the runway sanity check |
| Runway (months) | Reported, or derived from cash ÷ burn | If derived, mark `[Assumed — cash/burn]` |
| MRR / ARR | Revenue line | Label **contracted vs. recognized** |
| Growth (MoM / QoQ) | Delta vs. Snapshot prior period | Computed by Olli; note the comparison window |
| Headcount | Key Metrics table | Flag large swings (see below) |
| Core KPI (by vector) | Founder's chosen KPI | Per onboarding baseline; keep the set stable |
| Pipeline / LOIs | Progress / GTM section | Qualitative + quantitative |
| Key wins | TL;DR / Progress | 1–2 lines |
| Key risks / lowlights | Lowlights & Risks section | The primary flag-detection surface |
| Asks of Redstick | Asks section | Route intros/help to Cam; a blank asks field is itself a signal |
| Next milestone | Next Month / priorities | Anchor for follow-on and bridge decisions |

## Flag detection

Signals map to a severity and an action, tied to the
[crisis-management playbook](../Redstick-Knowledge-Base/09-playbooks/03-crisis-management.md).
High-severity flags are **drafted to Cam immediately, never silently logged.**

| Signal in the update | Severity | Action | Playbook tie |
|---|---|---|---|
| Runway < 6 mo (esp. < 4 mo cash, no term sheet) | 🔴 Critical | Same-day draft to Cam; get the *real* runway number; runway tree | [Crisis — Running out of runway](../Redstick-Knowledge-Base/09-playbooks/03-crisis-management.md) |
| "Confidentially exploring a sale" / acquihire interest | 🔴 Critical | Same-day draft; model liq-pref waterfall | Crisis — Acquihire; [exits](../Redstick-Knowledge-Base/09-playbooks/04-exits.md) |
| Co-founder friction / departure / equity dispute | 🔴 Critical | Same-day draft; separate-calls protocol; protect cap table | Crisis — Co-founder split |
| Down-round / recap language ("new money at a lower price") | 🟠 High | Draft this week; mark down, assess dilution | Crisis — Down round; [markups](../Redstick-Knowledge-Base/09-playbooks/02-markups.md) |
| Churn of a top logo / anchor LOI dies | 🟠 High | Draft this week; re-underwrite concentration; GTM help | Crisis — Key customer loss |
| MRR/ARR decline vs. prior period | 🟠 High | Draft; diligence *why* before drawing conclusions | Crisis — Pivot / customer loss |
| Missed a stated milestone; large unexplained headcount cut | 🟠 High | Draft; ask what slipped and why | Crisis — Pivot / runway |
| Metric contradicts a prior report (trend-integrity break) | 🟠 High | Flag the discrepancy; do **not** overwrite silently | Fraud/integrity watch — verify, don't assume |
| Raising a new round (up / flat) | 🟡 Watch | Flag for follow-on decision framework | [Markups & follow-on](../Redstick-Knowledge-Base/09-playbooks/02-markups.md) |
| Explicit ask for an intro / operator help | 🟡 Watch | Log the ask; draft to Cam to action within 2 business days | Onboarding — 2-day response commitment |
| Update overdue / missed | 🟡 Watch → 🟠 on 2nd miss | Draft one reminder; 2 consecutive misses → Cam reaches out | Onboarding — escalation |

Severity legend matches the playbook: 🔴 Critical = existential / act today · 🟠 High = act
this week · 🟡 Watch = monitor with a defined trip-wire.

## Outputs

- An **updated Notion Portfolio Snapshot row** (metrics, deltas, asks, reported-status).
- A **Gmail draft to Cam** with any flags (severity-sorted, source-quoted, playbook-linked) —
  only when flags fire; high-severity always.
- A **follow-on flag** into the markups decision framework when a raise is mentioned.
- A **cadence line** (reported / overdue) feeding the next
  [Weekly Operating Brief](./04-weekly-operating-brief.md).
- On a material event (down round, crisis trigger), a note routed toward LP-reporting per
  [`../Redstick-Knowledge-Base/06-lp-relations-fund-ops/`](../Redstick-Knowledge-Base/06-lp-relations-fund-ops/).

## Human-in-the-loop

- **Auto:** ingest, extract, and update the internal Snapshot (logged). This is a read-and-record
  loop — no outward action.
- **Draft only:** any reply to a founder (reminder, ask-acknowledgement, crisis outreach) is
  saved as a Gmail draft; nothing is sent until Cam sends it.
- **Cam decides:** every investment / follow-on / bridge / markdown decision. Olli recommends
  and assembles the math; Cam commits.
- **Always surfaced:** high-severity flags reach Cam the same day. A crisis signal is **never**
  silently logged and left for the next sweep.

## Guardrails

- **Never fabricate a KPI.** A missing figure is `[not reported]` — never inferred or
  back-filled to make a row look complete.
- **Provenance always.** Every figure cites the source update (email + date, or attachment +
  page). Transcript figures `[to confirm]`; derived figures `[Assumed]`.
- **Trend integrity.** If a founder's number contradicts prior reports, flag it — do not
  quietly overwrite the Snapshot. Repeated or material contradictions escalate as a possible
  integrity issue (fraud exception in the crisis playbook: verify, preserve the record).
- **Currency labels.** Every dollar is `USD` or `CAD`; fund reporting is USD, many companies
  report CAD.
- **Fund facts are hard-coded.** Any follow-on framing uses **$100K/$250K** and **MOIC** — a
  raise that would need a $500K/$1M check is SPV / future-fund territory, not a Fund I decision.
  If an update implies otherwise, flag the conflict; don't adopt it.
- **Search before write.** Match to the existing Snapshot row; never duplicate a company.
- **Privacy.** Founder data stays in Redstick systems; nothing goes to a third party without
  Cam's go.

## Failure modes & fallbacks

| Failure | Fallback |
|---|---|
| Attachment/dashboard unreadable | Extract from the email body; mark missing fields `[not reported]`; note the gap |
| Update is narrative-only, no KPI table | Extract prose signals; mark metrics `[not reported]`; nudge founder for the numbers |
| Sender doesn't match any Snapshot record | Flag to Cam (unknown sender or company missing from Snapshot); do not guess a match |
| Numbers don't reconcile (cash vs. burn vs. runway) | Flag the discrepancy to Cam; record both figures with provenance; don't pick one silently |
| Two updates in one period / correction email | Treat the latest as authoritative; keep the prior in history; note the correction |
| Update overdue | Draft one reminder; on 2nd consecutive miss, escalate to Cam as a relationship signal |
| Ambiguous crisis signal | Surface it anyway with `[Assumed]` framing — under-flagging a crisis is the costly error |

## Build plan

- **Crawl (now):** Cam/founder forwards an update to `olli@` → Olli extracts KPIs, updates the
  Snapshot, and drafts a flag brief on demand. Cadence tracked manually.
- **Walk:** Olli watches the inbox, auto-detects updates from known portfolio senders,
  auto-updates the Snapshot, and pushes high-severity flags to Cam the same day. Overdue-nudge
  drafts generated on schedule.
- **Run:** Full loop — Workflow 2 routes update PDFs in, transcripts auto-attach as context,
  cadence + flags feed the Weekly Operating Brief automatically, and follow-on signals open a
  pre-populated markups decision worksheet for Cam.

## Open questions

- Exact runway threshold for the same-day 🔴 flag — the crisis playbook uses < 4 mo for the
  runway tree; this spec flags at < 6 mo for early warning. Confirm the two tiers with Cam. `[confirm]`
- Should Olli auto-send the *overdue reminder* (low-stakes, templated) or always draft it? `[confirm with Cam]`
- How much weight to give a call transcript when it contradicts the written update — context
  only, or a flag in its own right? `[confirm]`
- Quarterly "state of the company" paragraph: auto-summarize across three months, or leave to
  Cam's read? `[confirm]`
