# 02 — Pipeline & CRM Ops

How the Notion **🔍 Deal Pipeline — Fund I** is run day to day. The pipeline is the
single source of truth for every live deal. If a deal is not in the pipeline, it does
not exist; if the pipeline is not current, we are flying blind.

> **Data source:** Notion Deal Pipeline (Fund I), data source ID
> `77829e04-0a0c-4ee6-94d5-1807b9ea0241`. Canonical fund facts:
> [`../../CLAUDE.md`](../../CLAUDE.md). Triage mechanics:
> [deal-triage SKILL](../../skills/deal-triage/SKILL.md).

---

## Golden rules

1. **Search before you create. Update if it exists. Never duplicate.** Every triage
   and every intake searches the data source by company name first. Duplicates corrupt
   funnel metrics and split a deal's history.
2. **One company = one record.** All history (multiple touches, re-triage after new
   docs) lives on the single record. Movement is captured by changing the Stage, not by
   making a new row.
3. **Every stage move has a date and a reason.** No silent moves. A deal that advances
   or dies records why.
4. **The repo wins on process; Notion holds live data.** Process/frameworks change in
   this repo; the pipeline database is where the live deals live. Don't encode process
   rules only in Notion.

---

## Stages — mapped to the 7-stage diligence pipeline

Pipeline Stage maps 1:1 to the underwriting pipeline in
[`../03-diligence-underwriting/`](../03-diligence-underwriting/). A deal's Stage is
simply the furthest gate it has cleared.

| # | Pipeline stage | Diligence gate (section 03) | Question answered | Typical exit |
|---|---|---|---|---|
| 0 | **Inbound / Logged** | (pre-triage intake) | Complete package received? | → Triaged or → request docs |
| 1 | **Triaged** | 1. Deck Screen (15–30 min) | Thesis fit? | ADVANCE / WATCH / PASS |
| 2 | **Founder Call** | 2. Founder Call (45–90 min) | Founder signal? | → Data Room or Pass |
| 3 | **Data Room** | 3. Data Room (4–8 hr) | Diligence feasible? | → References or Pass |
| 4 | **References** | 4. References (3–5 calls) | Integrity + track record? | → Tech DD or Pass |
| 5 | **Technical DD** | 5. Technical DD (6–12 hr) | Technical risk acceptable? | → IC or Pass |
| 6 | **IC Memo** | 6. IC Memo (8–12 hr) | Risk-adjusted return ≥ 5×? | IC decision |
| 7 | **Terms & Close** | 7. Terms & Close | Terms acceptable? | → Invested or Pass |
| — | **Invested** | (closed) | — | Portfolio (section 04/05) |
| — | **Passed** | (terminal) | — | One-line rejection thesis logged |
| — | **Watch** | (parked) | Flip condition stated | Re-enters at flip |

**Terminal-state discipline.** Every deal ends in **Invested**, **Passed**, or **Watch**.
No deal sits in an active stage indefinitely — see the aging rule below. A **Watch**
deal must carry an explicit flip condition (the exact thing that would move it to
ADVANCE), copied from the triage.

---

## Fields

The record is populated primarily by the triage output (Step 5 of the SKILL). Required
fields:

| Field | Type | Populated by | Notes |
|---|---|---|---|
| Company | Title | Intake / triage | Unique key — search this first |
| Decision | Select | Triage | ✅ Advance / 👀 Watch / ❌ Pass — **at Redstick's terms** |
| Stage | Select | Olli + Cam | The furthest gate cleared (table above) |
| Diligence Stage | Select | Triage | Deck / Light Data Room / References Started / 3-4 Data Room / Full DD |
| Thesis Tag | Select | Triage | One of the four vectors, or `Off-Thesis` |
| Weighted Score | Number | Triage | X.X / 5.0 (40/25/15/15/5 weighting) |
| EV by Stage (MOIC) | Text | Triage | Fail/Acqui-hire/Base/Strong/Fund-returner + blended |
| EV Hurdles Pass? | Checkbox/Select | Triage | EV ≥ 2.0x and base MOIC ≥ 5x at Redstick's terms |
| Round | Text | Triage | Instrument, cap, discount, MFN, pro-rata |
| Check Size | Select | Triage | $100K / $250K (modeled both) — never founder's ask |
| Entry Ownership | Text | Triage | **Informational only — never a gate** |
| Founder(s) | Text | Triage | Names + background |
| Location + Currency | Text | Triage | Label USD/CAD |
| Traction Signal | Text | Triage | Best single, cited to doc + page |
| Strategic LP Fit | Multi-select | Triage | CDN / female / Indigenous / clean-tech / regional-dev |
| Portfolio Concentration | Text | Triage | Vector/geo concentration note |
| Follow-on Reserve | Text | Triage | Reserve assumption |
| Round Timing | Text | Triage | Days to close, lead status, committed co-investors |
| Key Pass Reason / Watch Condition | Text | Triage | Never "ownership too low" / "round too small" |
| Source | Select | Intake | Channel (see [`01-sourcing-channels.md`](./01-sourcing-channels.md)) |
| Date Triaged | Date | Triage | Triage completion date |
| Triage Doc | URL | **Olli, after Drive upload** | Left blank by triage; Olli pastes the Drive link |
| Next Action / Owner / Due | Text/Date | Cam + Olli | Set at weekly review; drives the pipeline forward |
| Last Touched | Date | Auto/manual | Drives the aging rule |

**Currency discipline.** Every dollar figure carries `USD` or `CAD` (many deals are
CAD; fund reporting is USD). This is a hard rule from `CLAUDE.md`.

---

## Hygiene rules

- **48h triage SLA.** Any *complete* inbound package is triaged within 48 hours of
  landing. "Complete" = enough to run the triage per Step 0 of the SKILL (at minimum a
  deck; ideally a Light Data Room). Incomplete packages get a templated doc request and
  sit at **Inbound / Logged** until complete — the SLA clock starts when the package is
  complete.
- **No orphan records.** Every record has a Stage, a Decision (or Inbound status), a
  Source, and — if active — a Next Action with an owner and due date.
- **Aging / staleness.** An active deal (Stages 1–7) with no movement is flagged:
  **14 days** stale → surfaced at weekly review; **30 days** stale → must move, park to
  Watch (with a flip condition), or be killed to Passed. Dead deals get killed, not left
  to rot — a clean pipeline is an honest pipeline.
- **Kill with a thesis.** Every Pass records a one-line rejection thesis: why we passed
  and what would have changed our mind (calibration culture — see
  [`../../operating-cadence.md`](../../operating-cadence.md)). Passed deals are archived,
  not deleted; we revisit rejections for calibration.
- **Provenance.** Financial figures on the record cite their source (doc + page), per
  the SKILL's data-provenance rule. Inferences marked `[Assumed]`, conversation data
  `[to confirm on call]`.
- **Triage Doc closure.** A triaged deal is not "done" until the PDF is in Drive and the
  link is in the `Triage Doc` field. Olli owns closing this loop.

---

## Who updates when

| Event | Who | Action |
|---|---|---|
| Inbound lands | Olli | Search → create record at **Inbound / Logged** (or update existing); tag Source; check package completeness |
| Complete package | Olli (via SKILL) | Run triage within 48h → produce PDF + populate all triage fields → move to **Triaged** |
| Triage done | Olli | Upload PDF to Drive → paste link into `Triage Doc`; draft the message to Cam |
| Decision to advance | Cam | Confirm stage move (Founder Call → …); set Next Action + owner + due |
| Stage progress | Cam + Olli | Record each gate cleared, with date and reason |
| Deal dies | Cam | Move to **Passed** + one-line rejection thesis |
| Deal parked | Cam | Move to **Watch** + explicit flip condition |
| Deal closes | Cam | Move to **Invested**; hand off to construction (section 04) + services (section 05) |

---

## How Olli logs triage output

The triage SKILL produces four outputs in order; two of them touch the pipeline:

1. `[CompanyName]-Triage.pdf` → `/mnt/user-data/outputs/`.
2. **Notion entry** (SKILL Step 5): search the data source by company name → update if
   found, create only if not → populate every field in the table above, at **Redstick's
   terms**, leaving `Triage Doc` blank.
3. Draft message to Cam (5–7 sentences, incl. doc-gaps).
4. **Olli reminder:** upload the PDF to Google Drive → paste the link into the Notion
   `Triage Doc` field. This is the step that closes the record.

See the [deal-triage SKILL](../../skills/deal-triage/SKILL.md) Steps 5–6 and the output
checklist for the exact field list and the "no duplicates" enforcement.

---

## Weekly pipeline review ritual (Monday)

Part of the firm-wide weekly loop in
[`../../operating-cadence.md`](../../operating-cadence.md). Owner: **Cam + Olli**.
Output: an updated, honest Notion Deal Pipeline. ~30–45 minutes, run against a saved
Notion view sorted by Stage then Last Touched.

**Agenda:**

1. **New inbounds (since last Monday).** Confirm each was triaged within SLA; review any
   ADVANCE recommendations; decide founder-call scheduling.
2. **Stage moves.** Walk active deals (Stages 2–7). For each: advance (with reason),
   hold (with next action + due date), or kill.
3. **Aging sweep.** Every deal ≥14 days stale is addressed — move, park, or kill. Nothing
   ≥30 days stays in an active stage.
4. **Watch list flip check.** For each Watch deal, has its flip condition been met? If
   yes, re-enter the pipeline.
5. **Kills.** Confirm each Pass has a one-line rejection thesis logged.
6. **Funnel read.** Glance at stage counts vs. the target funnel in
   [`03-funnel-math.md`](./03-funnel-math.md). Are enough quality deals entering the top?
   Is any stage clogged? Under-supply at the top is a sourcing problem (fix Tier 1); a
   clog mid-pipeline is a diligence-throughput problem.
7. **Next-week actions.** Confirm intros to make, calls to book, docs to request. Olli
   updates the calendar/inbox; Cam owns the Friday close.

**Review health checks (a good pipeline looks like):** no active deal >30 days stale ·
every active deal has a dated next action + owner · every Pass has a thesis · Tier 1
channels produced at least some flow this month · stage counts roughly track the target
funnel shape.

---

*Cross-references: channels feeding the top → [`01-sourcing-channels.md`](./01-sourcing-channels.md) ·
the numbers this pipeline must hit → [`03-funnel-math.md`](./03-funnel-math.md) ·
the diligence gates behind each stage → [`../03-diligence-underwriting/`](../03-diligence-underwriting/).*
