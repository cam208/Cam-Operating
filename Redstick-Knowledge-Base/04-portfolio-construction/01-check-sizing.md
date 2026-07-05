# Check Sizing

## The rule

Fund I writes **$100K or $250K initial checks. Only.** Never the founder's ask, never
$500K, never $1M. Every deal is modeled at **both** sizes side by side (they produce the
same MOIC — MOIC is check-size-agnostic — but different dollar exposure and TVPI drag).

## $100K vs $250K — how we choose

Since MOIC is identical at both sizes, the choice is about **conviction and dollar
exposure**, not the deal's return multiple.

| Choose $100K when | Choose $250K when |
|---|---|
| Building a position / earlier conviction | High conviction, want more dollar exposure |
| More binary/higher-risk profile | Stronger evidence density (references, traction) |
| Want optionality to follow on rather than commit now | Want the initial position itself to be meaningful |
| Preserving shots across more names | Willing to accept 5% TVPI drag if it fails |

**TVPI drag if the company fails** (of the $5M fund): **2% per $100K**, **5% per $250K**.
That drag is the real cost of the larger check and the reason $250K requires more
conviction.

## The deployment model (illustrative)

A workable Fund I shape — refresh the live version monthly against actual deployment:

| Bucket | Capital | Notes |
|---|---|---|
| Initial checks | ~$2.5M | 15–20 companies at a $100K/$250K blend |
| Follow-on reserves | ~$2.5M | Concentrated into proven winners (see doc 03) |
| **Total** | **$5.0M** | Modeling figure; ~$4.725M net |

Illustrative initial-check blends to reach the target count:

| Blend | Math | Companies | Initial capital |
|---|---|---|---|
| All $100K | 20 × $100K | 20 | $2.0M |
| Mixed | 10 × $100K + 6 × $250K | 16 | $2.5M |
| Heavier $250K | 6 × $100K + 7 × $250K | 13 | $2.35M |

The exact blend flexes with deal quality and pacing; the guardrail is **15–20 initial
names** while preserving roughly half the fund for follow-on.

## Pacing

- **Deploy across the investment period, not in a rush.** Front-loading the fund forfeits
  the option to enter later vintages and to see how earlier bets develop.
- **Track deployment monthly**: % deployed, names funded, reserves remaining, average
  check. Update [`../../CLAUDE.md`](../../CLAUDE.md) §1 and this section.
- **Don't stretch to hit the count.** A weak deal taken to fill the portfolio is a
  guaranteed drag; discipline (a PASS) beats a forced check.
- **Don't starve reserves.** Over-deploying initial checks leaves nothing to concentrate
  into winners — the single most common small-fund construction error.

## The fund-returner test on every check

Regardless of size, each initial check is underwritten to: *can this one company return
the $5M fund at our entry terms?* If not, it is not a Fund I initial position. See the
fund-returner thresholds in
[`../01-fund-strategy-thesis/02-fund-parameters.md`](../01-fund-strategy-thesis/02-fund-parameters.md)
and the EV model in
[`../03-diligence-underwriting/03-financial-modeling-ev.md`](../03-diligence-underwriting/03-financial-modeling-ev.md).

## What check sizing is NOT allowed to do

- ❌ Flag a deal as "below an ownership floor" — Fund I has no ownership target.
- ❌ Pass a deal because "the round is too small" or "our check doesn't fit" — a $100K
  check participates in any round where the minimum is ≤ $100K.
- ❌ Use the founder's ask as the modeled check size.
