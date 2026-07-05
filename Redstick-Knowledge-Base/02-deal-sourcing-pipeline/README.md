# 02 — Deal Sourcing & Pipeline

How Redstick finds companies, moves them through the pipeline, and does the funnel
math that tells us whether we will build the portfolio we intend to. Sourcing is the
top of the machine; if the inbound is weak or off-thesis, no amount of downstream
discipline saves the fund.

> Canonical facts live in [`../../CLAUDE.md`](../../CLAUDE.md). Where anything here
> disagrees with that file, that file wins.

---

## The one-screen version

- **We are a $5M Fund I writing 15–20 checks of $100K or $250K.** That is the number
  the whole funnel has to feed. See [`03-funnel-math.md`](./03-funnel-math.md).
- **Warm operator/founder intros and the agrifood networks are our highest-signal
  channels.** Everything else is volume we filter hard. See
  [`01-sourcing-channels.md`](./01-sourcing-channels.md).
- **The Notion Deal Pipeline is the single source of truth for live deals.** Every
  inbound is logged; every triage output lands there. Stages map 1:1 to the 7-stage
  diligence pipeline in [`../03-diligence-underwriting/`](../03-diligence-underwriting/).
  See [`02-pipeline-crm-ops.md`](./02-pipeline-crm-ops.md).
- **Sourcing is a relationship business run on a give-to-get basis.** We build the
  network deliberately and review it quarterly. See
  [`04-network-strategy.md`](./04-network-strategy.md).

---

## Documents in this section

| # | Doc | What it covers |
|---|---|---|
| 1 | [Sourcing Channels](./01-sourcing-channels.md) | Every named channel — what it is, how we work it, expected quality/volume, owner, cadence. Channel scorecard. |
| 2 | [Pipeline & CRM Ops](./02-pipeline-crm-ops.md) | How the Notion Deal Pipeline is run: fields, stages, hygiene rules, ownership, weekly review ritual, 48h triage SLA, how Olli logs output. |
| 3 | [Funnel Math](./03-funnel-math.md) | Inbound → invested conversion assumptions and the worked funnel that proves the portfolio is buildable from realistic deal flow. |
| 4 | [Network Strategy](./04-network-strategy.md) | Deliberate relationship-building: co-investors, corporates, accelerators, banks, policy capital. Reciprocity model and quarterly review. |

---

## How this section connects

```
Sourcing channels ──► Notion Deal Pipeline ──► 7-stage diligence ──► IC ──► Invested
   (doc 01)              (doc 02, CRM)           (section 03)                 (section 04)
        ▲                                                                        │
        └──────────────── Network strategy (doc 04) feeds channels ◄────────────┘
                          Funnel math (doc 03) sizes the whole thing
```

- **Upstream:** the thesis and fund parameters in
  [`../01-fund-strategy-thesis/`](../01-fund-strategy-thesis/) define what is
  on-thesis and how many checks we are writing.
- **Midstream:** the [deal-triage skill](../../skills/deal-triage/SKILL.md) is the
  first hard gate applied to inbound, run by Olli within 48h of a complete package.
- **Downstream:** deals that clear triage enter the underwriting pipeline in
  [`../03-diligence-underwriting/`](../03-diligence-underwriting/) and, if funded,
  the construction model in [`../04-portfolio-construction/`](../04-portfolio-construction/).

## Owners & cadence

| What | Owner | Cadence |
|---|---|---|
| Channel working (intros, network) | Cam | Continuous; reviewed quarterly |
| Inbound intake + triage | Olli (via SKILL) | Within 48h of a complete package |
| Pipeline hygiene + stage moves | Olli + Cam | Weekly (Monday pipeline review) |
| Funnel metrics + conversion review | Cam | Quarterly |
| Network relationship review | Cam + Shane | Quarterly |

See [`../../operating-cadence.md`](../../operating-cadence.md) for the firm-wide rhythm.
