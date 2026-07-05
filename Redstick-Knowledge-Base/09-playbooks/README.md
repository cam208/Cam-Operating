# 09 — Playbooks

The most action-oriented section of the operating system. Everything upstream —
thesis, diligence, construction, services — decides *what* we do. These playbooks
decide *how we move* when a specific, high-stakes moment arrives: a wire clears, a
company raises its next round, a company hits a crisis, or a company exits.

> Canonical facts live in [`../../CLAUDE.md`](../../CLAUDE.md). Where anything here
> disagrees with that file, that file wins. These are procedures, not new policy —
> if a playbook implies a check size, fund size, or return unit different from
> `CLAUDE.md`, the playbook is wrong and must be corrected.

---

## Why these exist

Venture is high-variance and low-feedback. In a 15–20 company, $5M Fund I, a handful
of moments drive nearly all the outcome, and most of them arrive with little warning
and a short clock. We refuse to improvise those moments. Each playbook is a
pre-committed default — a checklist, a decision tree, a template — so that under time
pressure we execute a considered process instead of a panicked instinct.

Two Redstick truths shape all four:

- **We write small checks ($100K or $250K) and hold no control.** We usually hold an
  *observer* seat and information rights, not a board seat. Our leverage is
  influence, relationship, and being the most useful person in the room — never a
  vote. Every playbook is written for an influence-not-control investor.
- **Portfolio crises are inevitable in early-stage investing.** At a ≥20% bear-case
  fail floor across 15–20 companies, we expect multiple write-offs and at least one
  genuine crisis per active company over the fund life. We plan for it.

---

## Documents in this section

| # | Doc | The moment it governs | Core artifacts |
|---|---|---|---|
| 1 | [First 90 Days](./01-first-90-days.md) | Wire clears → first quarterly update | 90-day checklist; memo of record template |
| 2 | [Markups & Follow-on](./02-markups.md) | Company raises its next round | Signaling-risk guide; follow-on decision tree; SPV mechanics |
| 3 | [Crisis Management](./03-crisis-management.md) | A company hits a crisis | Crisis triage table; runway-emergency tree; comms guidance |
| 4 | [Exits](./04-exits.md) | A position becomes liquid (or dies) | Exit-decision table; secondary framework; write-off checklist |

---

## How this section connects

```
     Close ──► 01 First 90 Days ──► steady-state services (section 05)
                     │                        │
                     ▼                        ▼
             next round raised          crisis signal
                     │                        │
                     ▼                        ▼
             02 Markups & Follow-on    03 Crisis Management
                     │                        │
                     └────────► outcome ◄─────┘
                                   │
                                   ▼
                            04 Exits ──► distributions ──► LPs (section 06)
```

- **Upstream:** companies arrive from the [deal-triage
  skill](../../skills/deal-triage/SKILL.md) and
  [`../03-diligence-underwriting/`](../03-diligence-underwriting/). The memo of
  record written in doc 01 is the calibration baseline we grade every later playbook
  against at 6 / 12 / 24 months.
- **Alongside:** onboarding and support run in
  [`../05-portfolio-services/`](../05-portfolio-services/); reserve and SPV strategy
  in [`../04-portfolio-construction/`](../04-portfolio-construction/); governance and
  escalation in
  [`../05-portfolio-services/03-board-governance.md`](../05-portfolio-services/03-board-governance.md).
- **Downstream:** every markup, mark-down, and exit flows into the marks and metrics
  reported to LPs in
  [`../06-lp-relations-fund-ops/`](../06-lp-relations-fund-ops/).

---

## The calibration loop that binds all four

Every playbook feeds the same feedback discipline from
[`../../operating-cadence.md`](../../operating-cadence.md):

1. **Doc 01** writes the *memo of record* at close — our thesis, the fund-returner
   path, and the bear case, timestamped.
2. **Docs 02–04** are the events that test that memo. Each material event (markup,
   crisis, exit) is logged against the original memo.
3. **Annually**, every company is post-mortemed at 6 / 12 / 24 months: where did the
   memo hold, where did it break, and what does that teach the *next* underwrite?

Playbooks without a feedback loop are just paperwork. The loop is the point.

## Owners & cadence

| What | Owner | Cadence |
|---|---|---|
| First-90-days program | Cam (Olli coordinates) | Per company, on close |
| Memo of record + 6/12/24-mo revisits | Cam | On close; then semi-annual calibration |
| Follow-on / markup decisions | Cam + Shane | Ad hoc, on financing events |
| Crisis triage | Cam leads; Shane on ops/supply-chain | Ad hoc, on trigger |
| Exit decisions + write-offs | Cam + Shane | Ad hoc; write-offs swept quarterly |
| Playbook lessons-learned | Cam | Annually (calibration review) |

See [`../../operating-cadence.md`](../../operating-cadence.md) for the firm-wide rhythm.
