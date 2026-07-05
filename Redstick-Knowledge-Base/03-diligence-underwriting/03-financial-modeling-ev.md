# Financial Modeling & Expected Value

How Redstick turns a deal into a number. Fund I is evaluated on **MOIC** (the money
multiple), not IRR — decisions are made on the multiple. The executable, step-by-step
version is Section 4 of [`../../skills/deal-triage/SKILL.md`](../../skills/deal-triage/SKILL.md);
this doc is the reference for *why* the model is built this way.

## Non-negotiable modeling rules

1. **Model $100K and $250K side by side.** Never the founder's ask. Never $500K/$1M.
2. **Report EV as MOIC @ cap** — check-size-agnostic, so deals compare directly across
   the pipeline. (Absolute-dollar EV scales linearly with check size and is less useful.)
3. **Two cap scenarios:** (a) the founder's stated cap (reference only) and (b)
   Redstick's proposed cap. If (b) is TBD, the recommendation defaults to **WATCH**.
4. **Bear-case floor: ≥ 20% fail probability** at pre-seed/seed regardless of traction.
5. **Every financial figure cites its source** (document + page/section).

## Entry ownership (informational, not a gate)

- SAFE / convertible note: `entry_own = check_size ÷ cap`
- Priced round: `check_size ÷ post-money` (note: a pre-money option-pool refresh of
  5–10% dilutes investors before close — adjust if known)
- Discounted SAFE: model at cap-only **and** discount price; use whichever is more
  dilutive to the founder.

## Fail-probability by traction (bear-case anchors)

| Traction | Fail probability |
|---|---|
| Pre-revenue, no pilots, no product | 45–55% |
| Pre-revenue but LOIs / pilots in progress | 35–45% |
| Revenue < $500K, early customers, product live | 25–35% |
| Revenue > $500K, multiple paying customers, commercial hardware | 20–30% |

Never model below a **20%** fail floor — stage risk compounds with execution risk. If
you recalibrate, show original and adjusted EV with a one-line note.

## Dilution model

| Scenario | Rounds before exit | Retention calc | Retention % | Cumulative dilution |
|---|---|---|---|---|
| Acqui-hire | 0 | entry × 1.0 | 100% | 0% |
| Base case | Seed + A | entry × 0.80 × 0.80 | 64% | 36% |
| Strong exit | Seed + A + B | entry × 0.80 × 0.80 × 0.85 | 54.4% | 45.6% |
| Fund-returner | Seed + A + B | entry × 0.80 × 0.80 × 0.85 | 54.4% | 45.6% |

If prior SAFEs/notes are outstanding, mark all dilution figures
`[provisional — cap table required]` — they convert at the next priced round and worsen
Redstick's dilution before future rounds apply.

## The MOIC computation (compute in code, never by hand)

```python
entry_own  = check_size / cap            # 250000 / 8000000 = 0.03125 (3.13%)
diluted    = entry_own * 0.64            # base case retention
moic       = (diluted * exit_val) / check_size   # (0.02 * 100_000_000) / 250_000 = 8.0x
ev_contrib = prob * moic
```

Verification: if `exit_val > 0` and `entry_own > 0`, then `moic > 0`. Keep all values
in the same currency units (dollars, not millions). Exit valuations tie to
**ARR × multiple** — state which ARR (contracted vs recognized) and flag the gap.

## The EV table (present all scenarios + blended)

| Scenario | Prob | Exit val | Retention | Diluted own | MOIC | EV contrib |
|---|---|---|---|---|---|---|
| Fail | % | $0 | — | — | 0x | 0x |
| Acqui-hire | % | $ | 100% | % | x | x |
| Base case | % | $ (ARR×mult) | 64% | % | x | x |
| Strong exit | % | $ (ARR×mult) | 54.4% | % | x | x |
| Fund-returner | % | $ (ARR×mult) | 54.4% | % | x | x |
| **Blended EV** | **100%** | — | — | — | **X.Xx** | |

For WATCH/ADVANCE deals, add a **sensitivity table** (exit val ±30% × probability ±20%)
and flag if EV drops below 2.0x in the pessimistic corner.

**Acqui-hire caveat:** "entry × 1.0" assumes pro-rata distribution with no liquidation
preference stack above Redstick. If the preferred stack exceeds the exit price, MOIC
can be < 1x — flag explicitly.

## The hurdles (at Redstick's proposed terms)

| Hurdle | Bar |
|---|---|
| Blended EV | ≥ 2.0x |
| Base-case MOIC | ≥ 5x |
| No lens below 2.0 | required for ADVANCE |
| Fund-returner plausible? | single deal can return $5M (cite threshold) |

**Fund-returner thresholds ($5M fund, ~54.4% retention):**

| Cap | @ $100K | @ $250K |
|---|---|---|
| $4M | ~$368M | ~$147M |
| $6M | ~$551M | ~$221M |
| $8M | ~$735M | ~$294M |
| $10M | ~$919M | ~$368M |
| $15M | ~$1.38B | ~$551M |

**TVPI drag if the company fails:** 2% per $100K, 5% per $250K (of the $5M fund).

## Market stress test (mandatory before the number is final)

The EV model is only as good as its inputs. Before finalizing, run the five web-research
stress searches (deadline/regulatory, software-only TAM, competitive landscape, customer
demand, founder/company history) from the triage skill and recompute if research moves a
material input. See [`../../skills/deal-triage/SKILL.md`](../../skills/deal-triage/SKILL.md)
Step 3B.
