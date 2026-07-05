# Fund Parameters — Redstick Ventures Fund I

The hard economic constraints every decision operates inside. These are **hard-coded**.
If a task implies a different number, stop and flag the conflict.

## The numbers

| Parameter | Value | Notes |
|---|---|---|
| Fund | Redstick Ventures Fund I | First institutional fund |
| Fund size (modeling) | **$5.0M** | Live figure confirmed 2026-04-20 |
| Fund size (net, approx.) | ~$4.725M | Net of fees/expenses reference |
| Vintage / close | ~May 2025 | |
| Reporting currency | **USD** | Many deals are CAD — label every figure |
| Check size | **$100K or $250K only** | Model both, side by side, always |
| Prohibited check sizes | **$500K, $1M** | Future-fund territory — never model these for Fund I |
| Target ownership | **None** | Fund I is check-size-driven, not ownership-driven |
| Stage | Pre-seed → Series A | Concentration at pre-seed/seed |
| Geography | North America (US + Canada) | Cross-border is normal |
| Target portfolio | **15–20 companies** | Power-law construction (see doc 03) |
| Deployment (mid-2026) | ~1/3 deployed | Refresh monthly |
| Return unit | **MOIC** | Fund I is judged on the multiple, not IRR |
| Fund-returner bar | **$5M** returned by a single deal | The whole-fund test |
| Follow-on | Reserves + SPVs | Mechanics in section 4 |

## The check-size rule (the one people get wrong)

> The founder's raise amount is **irrelevant** to our check size. We write **$100K or
> $250K**. Every model shows both. We never use the founder's ask, and never model
> $500K or $1M.

Consequences that follow directly:

- **No ownership floor.** We never pass a deal for "ownership too low" or "round too
  small." A $100K check can ride in a $500K round or a $5M round.
- **Entry ownership is informational**, computed as `check ÷ cap`, recorded for the
  file — never a decision gate.

Entry-ownership reference (informational only):

| Cap | @ $100K | @ $250K |
|---|---|---|
| $4M | 2.50% | 6.25% |
| $6M | 1.67% | 4.17% |
| $8M | 1.25% | 3.13% |
| $10M | 1.00% | 2.50% |
| $15M | 0.67% | 1.67% |

## The return math

Fund I is evaluated on **MOIC** (money multiple), reported per deal as `MOIC @ cap`
so deals are comparable regardless of check size.

**Fund-returner test:** a single deal must be able to return the whole fund — **$5M**.
Assuming Seed + A + B dilution (~54.4% retention), the exit needed to return the fund:

| Cap | Fund-returner exit @ $100K | Fund-returner exit @ $250K |
|---|---|---|
| $4M | ~$368M | ~$147M |
| $6M | ~$551M | ~$221M |
| $8M | ~$735M | ~$294M |
| $10M | ~$919M | ~$368M |
| $15M | ~$1.38B | ~$551M |

**TVPI drag if a deal fails:** 2% per $100K check, 5% per $250K check (of the $5M fund).
This is why concentration discipline matters — see section 4.

## Portfolio-loss reality (why the bar is high)

At pre-seed/seed, the bear-case fail floor is **≥ 20%** regardless of traction, and
often far higher. Power-law construction assumes most of the portfolio returns little
and a small number of breakouts carry the fund. That is why every ADVANCE must clear:

- EV ≥ 2.0x at Redstick's proposed terms, and
- Base-case MOIC ≥ 5x,
- with no scoring lens below 2.0.

(Full underwriting hurdles: [`../03-diligence-underwriting/`](../03-diligence-underwriting/).)

## What changes these numbers

Only a GP decision, reflected first in [`../../CLAUDE.md`](../../CLAUDE.md) and then
here. Deployment %, portfolio count, and reserves are refreshed **monthly**; the rest
change only on an explicit fund decision (e.g. a Fund II would reset check sizes and
the fund-returner bar entirely).
