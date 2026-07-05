# Workflow 4 — Weekly Operating Brief (Auto Loop)

Every Monday before Cam is awake, Olli assembles **one** concise brief that pulls the
whole fund onto a single screen: what the pipeline is doing, what the portfolio is doing,
what the week's calendar holds, and — most importantly — the handful of decisions and asks
that actually need Cam this week.

> This is the read-only capstone of the automation layer. It reads what
> [`./01-inbound-deal-triage.md`](./01-inbound-deal-triage.md),
> [`./02-remarkable-pdf-intake.md`](./02-remarkable-pdf-intake.md), and
> [`./03-portfolio-report-intake.md`](./03-portfolio-report-intake.md) have written into
> Notion and surfaces it. It writes nothing outward and decides nothing — it teases up
> Cam's decisions, it never makes them.

## Purpose

Give Cam a single, trustworthy Monday-morning read so the [weekly operating
loop](../operating-cadence.md) starts from signal, not from a cold inbox. The brief feeds
directly into **Monday pipeline review** (and previews Wednesday's portfolio check-in and
Friday's close) so no deal goes stale, no portfolio flag gets buried, and no meeting is
walked into unprepared. Because it is 100% read-only, it can run fully autonomously.

## Trigger

- **Scheduled:** every **Monday ~06:00 ET**, via a cron/scheduled Olli run (e.g. the
  `claude-code-remote` trigger facility described in [`./README.md`](./README.md#how-these-get-built)).
- **On-demand:** Cam says *"Olli, give me the brief"* (or forwards a mid-week "where do we
  stand?") — same pipeline, run ad hoc.

**SLA:** the scheduled brief is in Cam's inbox **before 07:00 ET Monday**.

## Inputs

| Source | What Olli pulls | Window |
|---|---|---|
| Notion Deal Pipeline (`77829e04-0a0c-4ee6-94d5-1807b9ea0241`) | New inbounds, stage moves, deals closing soon, stale/no-movement deals | Since last brief (7 days) |
| Notion Portfolio Snapshot | Companies reported vs. overdue, active flags raised by [Workflow 3](./03-portfolio-report-intake.md), markups/rounds in progress | Current state + 7-day delta |
| Google Calendar | The week ahead — founder calls, LP meetings, IC sessions, board seats | Mon–Sun |
| Gmail | Unanswered high-priority threads (founders, LPs, warm intros) needing Cam | Open + last 7 days |
| Otter.ai / Limitless *(optional)* | Key takeaways / commitments from last week's meetings | Prior 7 days |
| [`../CLAUDE.md`](../CLAUDE.md) §1 + [fund parameters](../Redstick-Knowledge-Base/01-fund-strategy-thesis/) | Deployment snapshot: fund size, % deployed, reserves, portfolio count | Refreshed monthly |

## Pipeline

1. **Load context.** Read [`../CLAUDE.md`](../CLAUDE.md), the [operating
   cadence](../operating-cadence.md), and the crisis/flag conventions from the [portfolio
   intake spec](./03-portfolio-report-intake.md). Anchor all fund facts to §1.
2. **Query the pipeline.** Pull the Deal Pipeline and bucket rows: *new this week*,
   *advanced a stage*, *closing this week*, *stale (no movement past its stage SLA)*.
3. **Query the portfolio.** Pull the Portfolio Snapshot: active flags (severity-ranked),
   who is overdue on their update, and any live markup/round events.
4. **Read the week.** Pull the calendar Mon–Sun; tag each meeting (founder / LP / IC /
   board / internal) and attach a one-line prep note sourced from Notion or last week's
   transcript.
5. **Scan the inbox.** Identify high-priority unanswered threads that need Cam (not
   routine). Do **not** draft replies here — just surface them.
6. **Refresh the deployment snapshot.** Pull % deployed, reserves, and portfolio count
   from `../CLAUDE.md` §1 / fund parameters. Timestamp it and note the "as of" date.
7. **Rank the asks.** Synthesize the **Top 3 things needing Cam this week** — the
   decisions and asks with the highest cost of delay, drawn from the buckets above.
8. **Assemble & deliver.** Render the brief (template below) and deliver it (see Outputs).
   Every figure carries a source; anything stale or uncertain is marked.

## Brief structure

The brief always renders these six sections, in this order:

1. **Top 3 things needing Cam this week** — the decisions/asks with the highest cost of
   delay, each with a one-line "why now" and a pointer to the source row/thread.
2. **Pipeline** — four sub-buckets: *new*, *advancing*, *closing this week*,
   *stale / needs-kill* (per the Monday "dying deals killed" ritual).
3. **Portfolio** — active flags severity-ranked (🔴/🟡/🟢, per [Workflow
   3](./03-portfolio-report-intake.md) / the [crisis
   playbook](../Redstick-Knowledge-Base/09-playbooks/)), who's overdue on updates, and any
   markups/rounds in progress.
4. **Calendar: the week ahead** — meetings by day with prep notes.
5. **Deployment snapshot** — % deployed, reserves, portfolio count vs. the 15–20 target
   (from `../CLAUDE.md` §1; refreshed monthly, "as of" dated).
6. **Follow-ups from last week** — commitments/asks from the prior brief and last week's
   meetings, with status.

### Illustrative example brief

> **⚠️ ILLUSTRATIVE ONLY — synthetic placeholder data, not real pipeline/portfolio
> figures.** The live brief pulls every number from Notion and `../CLAUDE.md`.

---

**Redstick Weekly Operating Brief — Mon [illustrative date]** · prepared by Olli · read-only

**① Top 3 needing Cam this week**
1. **[Company A]** closes Thu — final $100K vs $250K call is yours; IC memo is done, scorecard 4.1/5.0. *(source: Pipeline row + IC memo)*
2. **[Portfolio Co B]** 🔴 flagged — <3 mo runway per last update; decide bridge vs. hold before Wed check-in. *(source: Portfolio Snapshot flag, Workflow 3)*
3. **[LP name]** awaiting your reply on the Q2 update thread (7 days open). *(source: Gmail, high-priority)*

**② Pipeline**

| Bucket | Deals |
|---|---|
| New this week | 3 inbound ([Co C] robotics, [Co D] CV/sensing, [Co E] off-thesis→quick pass) |
| Advancing | [Co F] Founder Call → Data Room; [Co G] References → Technical DD |
| Closing this week | [Company A] (Thu) |
| Stale / needs-kill | [Co H] — 21 days no movement at Data Room; recommend PASS + one-line thesis |

**③ Portfolio**

| Severity | Company | Flag |
|---|---|---|
| 🔴 | [Portfolio Co B] | Runway <3 mo — decision needed |
| 🟡 | [Portfolio Co I] | Key hire departed; watch |
| 🟢 | [Portfolio Co J] | Term sheet for Series A in progress (potential markup) |

*Overdue on updates:* [Portfolio Co K] (report was due last Wed).
*Markups/rounds in progress:* [Co J] Series A term sheet under review.

**④ Calendar — week ahead**

| Day | Meeting | Prep note |
|---|---|---|
| Mon | Pipeline review (Cam + Olli) | This brief is the input |
| Tue | Founder call — [Co F] | Data-room gaps: cap table, LOIs *(to confirm on call)* |
| Wed | Portfolio check-in | [Co B] bridge decision + [Co K] chase |
| Thu | [Company A] close | Confirm check size + wire per governance checklist |
| Fri | Weekly close | Log decisions; confirm next-week intros |

**⑤ Deployment snapshot** *(as of [illustrative month], from `../CLAUDE.md` §1)*

| Metric | Value |
|---|---|
| Fund I size | $5.0M USD (~$4.725M net) |
| Deployed | ~1/3 of Fund I |
| Portfolio count | [n] of 15–20 target |
| Reserves remaining | $[x] USD [Assumed — confirm at monthly refresh] |

**⑥ Follow-ups from last week**
- [Co G] reference calls — 3 of 5 done, 2 scheduled this week. *(in progress)*
- Intro to [warm channel] — Cam to send; still in drafts. *(pending Cam)*

---

## Outputs

- A **Gmail draft or auto-sent email to Cam himself** — because the brief is internal and
  read-only, Olli may **auto-send to `cam@redstickvc.com`** (Cam → Cam is not an external
  action). No other recipient, ever.
- Optionally, a **Notion page** under the operating hub, one per week, for the archive/history.
- A durable record that the next brief reads for its **§6 follow-ups**.

> No external email, no calendar writes, no founder/LP contact. If the brief surfaces
> something that needs an outward action, it names it as an ask in §1 — it never performs it.

## Human-in-the-loop

| Action | Autonomy |
|---|---|
| Read pipeline / portfolio / calendar / inbox | ✅ Autonomous |
| Assemble the brief | ✅ Autonomous |
| Auto-send the brief **to Cam only** (internal) | ✅ Autonomous |
| Every decision the brief raises (advance, pass, kill, bridge, follow-on) | ⛔ Cam decides |
| Any reply to a founder/LP/third party it flags | ⛔ Draft only, per [`./README.md`](./README.md#human-in-the-loop-policy-non-negotiable) |

**Olli proposes, Cam commits.** The brief is a mirror and a prioritizer, not an actor.

## Guardrails

- **Cite every figure.** Each pipeline/portfolio/deployment number names its source (Notion
  row, `../CLAUDE.md` §1, transcript). Inferences `[Assumed]`; call data `[to confirm on call]`.
- **Never fabricate.** Pipeline and portfolio numbers are pulled live from Notion. If a
  source is empty or unreachable, say so — do not invent a plausible number.
- **Mark staleness.** The deployment snapshot refreshes monthly; always show its "as of"
  date and flag if it's overdue for a refresh.
- **Flag fund-fact conflicts.** If any source implies a fund size or check size that
  contradicts `../CLAUDE.md` §1 ($5.0M fund, $100K/$250K checks, MOIC, $5M returner bar),
  surface the conflict in §1 rather than silently reporting it.
- **Currency labels.** Every dollar figure is `USD` or `CAD`.
- **Read-only.** The workflow performs no external or irreversible action, full stop.

## Failure modes & fallbacks

| Failure | Fallback |
|---|---|
| Notion pipeline/snapshot unreachable | Deliver the brief with that section marked `⚠️ data source unavailable`; do not fabricate |
| Calendar API empty / down | Note "calendar unavailable"; render the other five sections |
| Deployment snapshot stale (>1 mo old) | Show last-known figures with `[stale — monthly refresh overdue]` and add refresh to §1 asks |
| No new pipeline/portfolio activity | Say so plainly ("quiet week") rather than padding the brief |
| Conflicting fund fact in a source | Report `../CLAUDE.md` §1 as truth; list the conflict as an ask |
| Scheduled run misses 06:00 | On-demand trigger still available; log the miss for the ops review |

## Build plan

- **Crawl (now):** Cam says *"Olli, give me the brief"* → Olli queries Notion + Calendar +
  Gmail on demand and returns the six-section brief in chat / as an email draft.
- **Walk:** Scheduled Monday 06:00 ET run auto-assembles and **auto-sends to Cam**, with a
  Notion archive page per week and working §6 follow-up carry-over.
- **Run:** Brief becomes the live spine of the [weekly loop](../operating-cadence.md) —
  pulls the monthly-refreshed deployment snapshot automatically, ranks asks by cost of
  delay, and one-click hands each ask into its owning workflow (triage / portfolio / close).

## Open questions

- Exact delivery time and channel — 06:00 ET email vs. a Notion page vs. both? `[confirm with Cam]`
- Should §1 cap at 3 asks, or flex to 5 in a heavy week? `[confirm]`
- Include Otter/Limitless meeting recaps by default, or only when Cam asks? `[confirm]`
- Does the on-demand mid-week brief carry the same §6 follow-up ledger, or a lighter form? `[confirm]`
