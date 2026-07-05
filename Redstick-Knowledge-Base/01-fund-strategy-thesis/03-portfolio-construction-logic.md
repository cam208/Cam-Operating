# Portfolio Construction Logic

The strategic "why" behind the portfolio shape. The operational "how" — exact check
sizing, reserve mechanics, concentration limits, SPVs — lives in
[`../04-portfolio-construction/`](../04-portfolio-construction/). Read this first.

## The power law governs everything

Early-stage venture returns follow a power law: a small number of investments produce
the overwhelming majority of returns, and most investments return little or nothing.
A seed fund is not built by being right on average — it is built by owning enough of
the eventual breakout(s) to return the whole fund several times over.

Two consequences shape Fund I:

1. **You must have enough shots.** With most outcomes near zero, too few positions and
   you can miss the breakout entirely. This pushes toward a **larger** number of names.
2. **Each shot must be able to matter.** If a position is too small to move the fund
   even in a great outcome, it is a donation, not an investment. This pushes toward
   **fewer, larger** positions.

Portfolio construction is the resolution of that tension.

## Why 15–20 companies

$5M fund, $100K–$250K checks. Reserving roughly half of the fund for the initial
checks and holding the rest for follow-on into the winners lands the initial-portfolio
count in the **15–20** range.

Illustrative (see section 4 for the live model):

| Initial check mix | Initial capital | ~Companies | Reserve for follow-on |
|---|---|---|---|
| Blend of $100K / $250K | ~$2.5M | **~15–20** | ~$2.5M |

15–20 is enough shots to catch a power-law winner while keeping each initial position
large enough that a fund-returner outcome actually returns the fund (see the
fund-returner table in [`02-fund-parameters.md`](./02-fund-parameters.md)).

## The fund-returner lens on every deal

Because the power law does the work, **every** initial investment is underwritten to a
simple question:

> *Can this single company, at our entry terms, plausibly return the entire $5M fund?*

If the honest answer is "no, even in the best realistic case," it is not a Fund I
initial check — regardless of how safe or nice the deal looks. This is the
"fund-returner bar" from the diligence process, and it is why a low-risk, capped-
upside deal can still be a PASS.

## Diversification we want vs. diversification we don't

| We deliberately diversify across | We deliberately concentrate in |
|---|---|
| Companies (15–20 shots) | The thesis — all four vectors are food-productivity |
| The four technology vectors | Stage — pre-seed/seed entry |
| Entry timing across the deployment window | Geography — North America |
| Sub-sectors within food (farm → consumer) | Conviction — no "spray and pray" |

We do **not** diversify away from the thesis to chase a hot non-food deal. Thesis
discipline is the fund's identity and its diligence edge.

## Concentration guardrails (summary)

Detailed limits live in section 4. The principles:

- **No single initial position dominates** the initial portfolio's capital.
- **Concentration within a sub-vector is monitored** — too many near-identical bets
  (e.g. five produce-grading CV companies) is correlated risk, not diversification.
  The deal-triage skill flags portfolio concentration (Low/Med/High) on every deal.
- **Follow-on concentrates into proven winners**, not to defend losers ("don't throw
  good money after bad" — see [`../09-playbooks/02-markups.md`](../09-playbooks/02-markups.md)).

## How this connects to the rest of the OS

- **Sourcing** must supply enough quality inbound to fund 15–20 names with discipline
  → [`../02-deal-sourcing-pipeline/03-funnel-math.md`](../02-deal-sourcing-pipeline/03-funnel-math.md).
- **Diligence** enforces the fund-returner bar and the ≥5x base-MOIC hurdle
  → [`../03-diligence-underwriting/`](../03-diligence-underwriting/).
- **Reserves & follow-on** decide how the second half of the fund concentrates
  → [`../04-portfolio-construction/`](../04-portfolio-construction/).
