# Concentration Limits

Diversification and concentration are both deliberate. We spread across companies and
vectors; we concentrate on the thesis and, later, on winners. The guardrails below keep
correlated risk from masquerading as diversification.

## Position-level guardrails

| Guardrail | Rule | Why |
|---|---|---|
| **Initial position size** | $100K or $250K only | No single initial check can sink the fund; keeps 15–20 shots |
| **No dominant initial position** | No initial check disproportionately large vs the rest | Preserves power-law shot count |
| **Total exposure per company** | Initial + follow-on managed against reserves | Follow-on concentrates into winners, but not to the point one name is the whole fund |
| **Fund-returner test** | Every initial check must be able to return $5M | A capped-upside position is a drag, not a diversifier |

Note: because Fund I is check-size-driven, position sizing is expressed in **dollars and
shot-count**, not ownership percentage. There is no ownership floor or ceiling.

## Sub-vector concentration

The four vectors are the intended diversification axis. Within them, watch for
**correlated bets**:

| Concentration | Interpretation | Action |
|---|---|---|
| **Low** | 0–1 existing holdings in the same sub-vector | Proceed |
| **Medium** | 2–3 in the same sub-vector | Proceed with eyes open; note correlation in IC memo |
| **High** | 4+ near-identical bets (e.g. multiple produce-grading CV companies) | Raise the bar — is this real diversification or the same bet five times? |

Every triage rates portfolio concentration Low/Med/High against current holdings (see
[`../03-diligence-underwriting/05-sector-dd.md`](../03-diligence-underwriting/05-sector-dd.md)
and the deal-triage skill). Five companies exposed to the same customer, the same
regulatory catalyst, or the same third-party platform are one correlated position, not
five.

## Correlated-risk lenses (beyond sub-vector)

Check for hidden correlation across the portfolio:

- **Customer concentration** — many portfolio companies selling to the same handful of
  grocery chains / processors. If that buyer freezes spend, several bets stall at once.
- **Platform dependency** — multiple companies reliant on the same third-party model/API;
  one pricing change hits them all.
- **Regulatory catalyst** — multiple bets that only work if the same regulation/deadline
  holds.
- **Geographic / FX** — CAD-heavy exposure; monitor USD/CAD concentration for reporting.

## Deliberate concentration we accept

- **The thesis.** 100% food-productivity. We do not diversify into non-food to reduce
  sector risk — thesis discipline is the fund's identity and diligence edge.
- **Stage.** Pre-seed/seed entry across the board.
- **Winners (later).** Reserves concentrate into the companies that prove out — see
  [`03-spv-follow-on.md`](./03-spv-follow-on.md). Concentrating into winners is the point;
  concentrating into losers to "defend" them is the error.

## Monitoring cadence

- **Monthly** — refresh deployment, reserves remaining, and per-company exposure.
- **Quarterly** — recompute sub-vector and correlated-risk concentration across the full
  portfolio; flag any lens drifting to High.
- **On every new deal** — the triage's concentration rating is a required field, not
  optional.
