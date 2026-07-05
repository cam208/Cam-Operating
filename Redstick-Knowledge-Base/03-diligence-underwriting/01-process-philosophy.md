# Process Philosophy

Redstick employs a structured **7-stage pipeline with hard gates** to replace
single-point-of-failure judgment with distributed validation. Process discipline
outperforms expert intuition in high-variance, low-feedback environments like venture.

## Core principles

| Principle | Implementation |
|---|---|
| **Reversibility test** | Only kill deals for strong evidence; at the IC memo, reverse the burden of proof. If uncertain, push to references/tech DD rather than killing. |
| **Conviction over speed** | Better to decline a good deal than deploy behind qualified conviction. No FOMO premium. |
| **Evidence density** | Founder's own words < proven behavior < independent verification. Reference calls > founder-provided references. |
| **Disconfirmation focus** | Actively hunt for reasons **not** to invest. Pattern-matching and the halo effect are our largest blind spots. |
| **Calibration culture** | Post-mortem every rejection and investment at 6/12/24 months. Update the thesis quarterly. |

## The 7-stage pipeline

Each stage ends in a hard gate. A deal advances only by passing the gate; otherwise it
is killed (with a one-line reason for calibration) or parked as WATCH with an explicit
flip condition.

```
STAGE 1: Deck Screen      (15–30 min)   [GATE: Thesis fit?]
   ↓
STAGE 2: Founder Call     (45–90 min)   [GATE: Founder signal?]
   ↓
STAGE 3: Data Room        (4–8 hr)      [GATE: Diligence feasible?]
   ↓
STAGE 4: References       (3–5 calls)   [GATE: Integrity + track record?]
   ↓
STAGE 5: Technical DD     (6–12 hr)     [GATE: Technical risk acceptable?]
   ↓
STAGE 6: IC Memo          (8–12 hr)     [GATE: Risk-adjusted return ≥ 5×?]
   ↓
STAGE 7: Terms & Close    (negotiation) [GATE: Terms acceptable?]
```

These stages map directly to the Notion Deal Pipeline stages and to the diligence-stage
classification in the triage skill (Deck → Light Data Room → References Started → 3/4
Data Room → Full DD).

## Five-lens scoring model (live weighting)

`(Founder×0.40) + (Market×0.25) + (Tech×0.15) + (UnitEcon×0.15) + (DealTerms×0.05)` = **X.X / 5.0**

| Lens | Weight | Assessment focus |
|---|---|---|
| **Founder** | 40% | Domain experience, team composition, decision-making, resilience |
| **Market** | 25% | TAM (bottoms-up), competitive intensity, willingness to pay |
| **Technology** | 15% | IP defensibility, engineering risk, proof-of-concept |
| **Unit Economics** | 15% | CAC, LTV, path to >60% gross margin |
| **Deal Terms** | 5% | Cap, MFN/pro-rata, dilution path |

> **Weighting history:** the original model weighted Founder 50 / Market 20 / UnitEcon
> 10 / Ownership 5. It was superseded on **2026-04-20** by the 40/25/15/15/5 weighting
> above (Fund I is check-size-driven, so "ownership" became "deal terms"). Use the
> current weighting. Scoring anchors: 0 = red flag/no info · 1–2 weak · 3 adequate ·
> 4 strong · 5 exceptional.

**ADVANCE floor rule:** no lens may score below 2.0 for an ADVANCE. A sub-2.0 on any
lens caps the recommendation at WATCH.

## Kill criteria (hard stops)

Automatic rejection if **any** are present:

- Founder misrepresentation or lack of integrity
- Regulatory blockers preventing product launch for > 18 months
- No clear unit-economics path, or TAM < $500M
- Chronic team execution issues or founder-departure risk
- Unmitigated, undiversified technology risk within the portfolio

## Never a valid PASS reason for Fund I

Because Fund I is check-size-driven with no ownership target:

- ❌ "Ownership too low"
- ❌ "Round too small"
- ❌ "Check size doesn't fit" (if the founder's minimum check is ≤ $100K, we can participate)

A PASS must cite thesis fit, a red flag, or a failed EV/quality hurdle — never the
above.

## The three outcomes

| Outcome | Meaning |
|---|---|
| **ADVANCE** | Thesis fit, no red flags, no lens < 2.0, EV ≥ 2.0x, base MOIC ≥ 5x at Redstick's terms → schedule intro call / progress the stage |
| **WATCH** | On-thesis but marginal EV, missing data, a lens < 2.0, or cap TBD → record the exact condition that would flip it to ADVANCE |
| **PASS** | Off-thesis, a red flag, or failed hurdles → one-sentence reason (never ownership/round-size) |

Every rejection and investment is logged and revisited at 6/12/24 months. That feedback
loop — not any single call — is what makes the process compound.
