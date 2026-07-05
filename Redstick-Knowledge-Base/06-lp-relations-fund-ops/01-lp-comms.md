# 06.01 — LP Communications

The job here is simple to state and hard to do well: **no LP should ever be surprised.**
Not by a markdown, not by a capital call, not by a portfolio failure they read about
in the press first. We are a $5M Fund I. Our LPs took a bet on a two-person GP team
and an AI EA. The way we earn the right to raise Fund II is by communicating like a
firm three times our size — on a fixed cadence, in plain language, with the bad news
delivered as fast and as straight as the good.

> Canonical facts live in [`../../CLAUDE.md`](../../CLAUDE.md). Fee, carry, and
> distribution terms are read off the LPA — see [`03-fund-administration.md`](./03-fund-administration.md).

---

## Communication cadence

| Channel | Frequency | Owner | Audience | Purpose |
|---|---|---|---|---|
| **Quarterly LP letter** | 4×/year, within 45 days of quarter-end | Cam (Olli drafts) | All LPs | Deployment, marks, metrics, market view, asks |
| **Annual LP meeting** | 1×/year (Q1, on prior FY) | Cam + Shane | All LPs | Full-year review, portfolio deep-dives, live Q&A |
| **Year-end investor newsletter** | December | Cam (Olli drafts) | All LPs + close network | Narrative recap, thesis reflection, wins, what we learned |
| **Capital-call notice** | As deployment requires | Cam + fund admin | All LPs | Formal call per LPA notice period |
| **Ad-hoc material-event note** | As needed | Cam | All LPs (or affected) | Material markups, failures, key-person or strategy changes |
| **Strategic-LP policy report** | Quarterly + annual summary | Olli assembles | FCC, CFIN | Policy-outcome metrics on top of financials |

Rule of thumb: **quarterly is the floor, not the ceiling.** A material event (a
fund-returner markup, a portfolio failure, a founder departure, an FX or strategy
shift) gets its own note the week it happens — never held for the next quarterly.

---

## What goes in a quarterly LP update

Every quarterly letter carries the same spine so LPs can read it in five minutes and
compare quarter over quarter:

1. **Deployment** — capital called vs. committed, deployed vs. reserved, dry powder
   remaining, pace vs. plan (target 15–20 companies).
2. **Portfolio highlights** — 2–4 companies with the most movement this quarter
   (new customers, raises, milestones). Named only with founder consent.
3. **Fund metrics** — TVPI, DPI, RVPI, MOIC (net where stated). Gross vs. net labeled.
   See [`02-fund-reporting.md`](./02-fund-reporting.md) for definitions.
4. **New investments** — every new check this quarter: company, vector, stage, check
   size ($100K or $250K), instrument, cap, one-line thesis.
5. **Notable markups / markdowns / risks** — what moved and why, conservatively. Any
   position now carried above cost, any impairment, any company on the watch list.
6. **Market view** — one to three paragraphs of Redstick's read on AI/robotics for
   food productivity: what's changing in the four vectors, what it means for the fund.
7. **Asks** — specific, small, and honest. Intros, hiring help, LP-network deal flow,
   pilot customers for portfolio companies. Give LPs a way to add value.

Discipline: every number **cites its basis** (as-of date, FX rate, valuation event).
Marks are conservative by policy — cost until a priced round or material event.

---

## The quarterly LP letter template

```
Redstick Ventures — Fund I
Quarterly LP Letter · Q[X] [YYYY]
Reporting currency: USD · Marks as of [DATE] · FX: 1 USD = [X.XXXX] CAD
Prepared by: Cam Crowder, GP

---

Dear Partners,

[2–4 sentence opening: the one thing that mattered this quarter, in plain
language. Lead with substance, not throat-clearing.]

1) FUND SNAPSHOT (net to LPs unless noted)

| Metric                    | This Q      | Last Q      | Since inception |
|---------------------------|-------------|-------------|-----------------|
| Committed capital (USD)   | $5.0M       | $5.0M       | $5.0M           |
| Capital called (USD)      | $[  ]M ([ ]%) | $[  ]M    | —               |
| Capital deployed (USD)    | $[  ]M      | $[  ]M      | —               |
| Reserves held (USD)       | $[  ]M      | $[  ]M      | —               |
| Dry powder (USD)          | $[  ]M      | $[  ]M      | —               |
| Portfolio companies       | [  ]        | [  ]        | [  ]            |
| TVPI (net)                | [  ]x       | [  ]x       | —               |
| DPI (net)                 | [  ]x       | [  ]x       | —               |
| RVPI (net)                | [  ]x       | [  ]x       | —               |
| MOIC (gross, blended)     | [  ]x       | [  ]x       | —               |

[Note: MOIC is the fund's primary return unit. IRR is not reported for Fund I.]

2) NEW INVESTMENTS THIS QUARTER

| Company | Vector | Stage | Check (USD) | Instrument | Cap | One-line thesis |
|---------|--------|-------|-------------|------------|-----|-----------------|
| [ ]     | [ ]    | [ ]   | $[100/250]K | SAFE/Note  | $[ ]M | [ ]           |

3) PORTFOLIO HIGHLIGHTS
- [Company] — [what moved, cited]. Carried at [cost / $[ ]M, priced round DATE].
- [Company] — [milestone]. [Strategic-LP fit flag if relevant.]

4) MARKS, MARKDOWNS & RISKS
- Markups: [company — event that justified the mark, conservative basis].
- Watch list: [company — the risk, what we're doing about it]. No spin.
- Impairments: [company — status]. [If none: "No impairments this quarter."]

5) MARKET VIEW
[1–3 paragraphs: Redstick's read on AI & robotics for food productivity.
Tie to the four vectors. What's changing, and what it means for the fund.]

6) ASKS
- [Specific intro / hire / pilot customer / co-investor ask.]

Deployment remains on plan for a 15–20 company portfolio. As always, reach out
anytime — my line is open.

— Cam
cam@redstickvc.com · 519-919-2703
```

Keep the letter to **two to three pages**. LPs skim; the table does the heavy lifting.

---

## Capital-call communications

Capital calls are a formal, LPA-governed process (mechanics in
[`03-fund-administration.md`](./03-fund-administration.md)). The comms wrapper around
each call:

- **Notice period per the LPA** `[confirm with LPA]` — typically 10 business days;
  never surprise an LP with a call due tomorrow.
- **One notice, one number, one date.** Each notice states: amount called (USD),
  this LP's pro-rata share, wire instructions, due date, and cumulative called-to-date.
- **Pair every call with a purpose.** LPs fund faster and complain less when the notice
  says *what the capital is for* — "this call funds two new seed checks and reserves."
- **Confirm receipt in writing.** Fund admin reconciles; Cam sends a one-line thanks.
- **CAD-funding LPs:** state the USD amount, the FX assumption, and who bears the
  conversion. Any FCC/CAD-denominated commitment is normalized to the fund's USD books
  at the stated rate — flag the convention every time.

---

## How to handle bad news

Bad news is where LP trust is actually built or destroyed. The standing rules:

- **Speed beats polish.** A portfolio failure, key-person issue, or material markdown
  goes out within days — a short, straight note, not a delayed perfect memo.
- **LPs hear it from us first.** Never let an LP learn of a portfolio problem from
  press, LinkedIn, or another investor.
- **Name the number and the cause.** "Company X wound down. Our $[ ]K is written to
  zero — a [ ]% TVPI drag. Here is what happened and what we took from it." No hedging.
- **Own the lesson, not the excuse.** Redstick runs a calibration culture (every
  investment revisited at 6/12/24 months). Bad news is a data point we underwrite from,
  and we say so.
- **Expected, not catastrophic.** Remind LPs this is a power-law fund: the bear-case
  floor is ≥20% fail probability at pre-seed/seed *by design*. A failure inside the
  model is not the fund breaking — it is the fund working. Frame it that way, honestly.

A single failed $100K check is a ~2% TVPI drag; a $250K check ~5%. Put the magnitude
in the note so the LP calibrates instead of catastrophizes.

---

## Strategic-LP reporting (FCC / CFIN and policy capital)

Redstick's LP base includes strategic and policy-oriented capital — Farm Credit Canada
(FCC) and the Canadian Food Innovation Network (CFIN) — whose mandates go beyond
financial return. These LPs get the standard financial pack **plus** a policy-metrics
supplement. We tag these flags at triage (see the deal-triage SKILL) so the data is
already captured by the time we report.

**Policy metrics tracked and reported (portfolio-level, quarterly + annual summary):**

| Metric | What we report | Why it matters |
|---|---|---|
| Canadian founders / companies | # and % of portfolio; $ deployed into Canadian cos (USD + CAD) | Core FCC/CFIN mandate; Canadian agrifood innovation |
| Female founders | # and % of portfolio companies with a female founder/co-founder | Diversity and inclusion reporting |
| Indigenous founders | # and % with Indigenous founder/co-founder | Reconciliation / inclusion mandate |
| Clean-tech angle | # of companies with a clean-tech / sustainability dimension (emissions, inputs, waste) | Climate and clean-growth reporting |
| Regional economic development | Companies located outside major hubs; jobs/regional impact where known | Rural / regional development mandate |
| Cross-border capital flow | USD deployed into CAD-domiciled companies, at stated FX | Canadian capital-attraction narrative |

**Reporting conventions for strategic LPs:**

- Report policy metrics **as counts and percentages**, with the deployed-dollar figure
  in both USD (fund books) and CAD (policy relevance), at the stated FX rate.
- Do **not** overstate. If a founder self-identifies, we report it; we do not infer
  Indigenous or female-founder status. Missing data is reported as "not disclosed."
- The **annual policy summary** rolls the quarterly flags into one narrative for FCC and
  CFIN, tied to their specific mandate language `[confirm exact reporting fields with
  each strategic LP's side letter]`.
- Financial-return reporting for strategic LPs is **identical** to all other LPs — same
  TVPI/DPI/MOIC, same conservative marks. The policy supplement is additive, never a
  substitute for the fund numbers.

> Side-letter reporting obligations vary by LP. The exact fields, frequency, and
> format FCC and CFIN require are governed by their subscription/side-letter documents —
> `[confirm with LPA / side letters]`. This doc defines the default; the side letter wins.
