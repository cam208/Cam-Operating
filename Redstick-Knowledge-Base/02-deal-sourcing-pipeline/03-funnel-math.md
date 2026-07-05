# 03 — Funnel Math

The arithmetic that connects "deals we see" to "portfolio we build." A fund either does
this math deliberately or discovers, two years in, that its top-of-funnel was never big
enough to construct the portfolio it promised its LPs. This document sizes the machine.

> All figures are **illustrative planning assumptions**, not actuals or promises. They
> are calibrated to Fund I's real parameters from [`../../CLAUDE.md`](../../CLAUDE.md):
> **$5.0M fund (~$4.725M net), 15–20 checks of $100K/$250K, MOIC-driven, power-law
> construction.** Update the conversion rates quarterly against real pipeline data
> (see [`../../operating-cadence.md`](../../operating-cadence.md)).

---

## What the portfolio requires

| Parameter | Value | Source |
|---|---|---|
| Target portfolio | 15–20 companies | `CLAUDE.md` §1 |
| Planning target (this doc) | **18 investments** | midpoint |
| Check size | $100K or $250K | `CLAUDE.md` §1 |
| Investment period | ~3 years | [Assumed] planning horizon |
| Net investable | ~$4.725M | `CLAUDE.md` §1 |

**Capital sanity check (deferred to [`../04-portfolio-construction/`](../04-portfolio-construction/)):**
18 companies at a blended initial check (~$130–180K, weighted toward $100K) consumes
roughly half of net capital, leaving the balance in reserves for follow-on into
winners. The point here is only that **18 checks is consistent with the fund's capital**
— construction owns the exact split. The sourcing job is to *find and qualify* those 18.

---

## The funnel stages

Six stages, matching the pipeline in
[`02-pipeline-crm-ops.md`](./02-pipeline-crm-ops.md), which in turn maps to the 7-stage
diligence process in [`../03-diligence-underwriting/`](../03-diligence-underwriting/).

| Stage | What it means | Gate that filters it |
|---|---|---|
| **1. Inbound** | Every deal surfaced, all channels | Completeness + on-thesis |
| **2. Triaged** | Complete package run through the triage SKILL | 48h SLA; incomplete deals held out |
| **3. Founder Call** | ADVANCE recommendation → intro call booked | Triage decision (thesis fit, no red flags, EV ≥ 2.0x) |
| **4. Data Room** | Diligence-grade materials reviewed | Founder signal from the call |
| **5. IC** | Full memo to Investment Committee | Survives references + technical DD |
| **6. Invested** | Term sheet signed, deal closed | IC decision + terms |

> Stages 4→5 fold references (gate 4) and technical DD (gate 5) into the walk from Data
> Room to IC; the CRM tracks those sub-gates individually, the funnel model rolls them
> up.

---

## Conversion assumptions (blended across channels)

These are **blended** rates. In reality Tier 1 channels (operator/founder intros,
THRIVE, portfolio referrals) convert several times better than Tier 3 inbound at every
stage — which is exactly why sourcing effort concentrates there (see
[`01-sourcing-channels.md`](./01-sourcing-channels.md)). The blend below assumes the
target channel mix (~55% of *invested* from Tier 1).

| Transition | Conversion | Rationale |
|---|---|---|
| Inbound → Triaged | **70%** | ~30% of raw inbound is incomplete, withdrawn, or obviously off-thesis before triage |
| Triaged → Founder Call | **18%** | Triage ADVANCE rate — deliberately selective; most triaged deals are WATCH/PASS |
| Founder Call → Data Room | **45%** | Founder signal holds up in under half of first calls |
| Data Room → IC | **30%** | Diligence, references, and tech DD kill most deals here — the deepest cut |
| IC → Invested | **55%** | IC is a real gate; terms and final conviction remove some memo'd deals |

**Cumulative:** Inbound → Invested ≈ **0.94%**. Roughly **1 investment per ~107 raw
inbound**, or **1 per ~75 triaged** deals. This is in line with typical early-stage
fund yields (~1%), and it is the number that sizes everything else.

---

## Worked funnel — over the fund's investment period

Solving backward from 18 investments, then reading the whole cascade forward:

| Stage | Conversion to next | Count (fund life) | Per year (÷3) | Rough per week |
|---|---|---:|---:|---:|
| **Inbound** (all channels) | ×0.70 | **~1,925** | ~640 | ~12 |
| **Triaged** (complete pkgs) | ×0.18 | **~1,345** | ~450 | ~9 |
| **Founder Call** | ×0.45 | **~242** | ~80 | ~1.5 |
| **Data Room** | ×0.30 | **~109** | ~36 | — |
| **IC** | ×0.55 | **~33** | ~11 | — |
| **Invested** | — | **~18** | ~6 | — |

**How to read it.** To land ~18 checks, Redstick needs to *see* on the order of ~1,900
deals and *triage* ~1,345 complete packages over three years — about **9 triages a
week**. That is a volume Olli's automated triage (48h SLA) is built to absorb; the
human-expensive stages (founder calls onward) stay small and manageable at ~1–2 calls a
week and ~1 IC memo a month.

---

## The "quality inbound" cut

Raw inbound volume is a vanity metric. What actually feeds the portfolio is **on-thesis,
qualified inbound** — deals that are genuinely in one of the four vectors, at
pre-seed–Series A, in North America. Off-thesis volume is filtered cheaply and does not
convert.

If ~30% of raw inbound is on-thesis quality (higher than a generalist fund's, because
much of our flow comes from curated Tier 1/2 channels):

| Metric | Value |
|---|---|
| Raw inbound needed (fund life) | ~1,925 |
| **Quality (on-thesis) inbound needed** | **~575** (~190/year, ~4/week) |
| Quality inbound → Invested | ~3.1% (≈ 1 in 32) |

**The strategic implication.** The fund does *not* need a firehose of cold decks. It
needs roughly **4 genuinely on-thesis deals a week**. That is achievable almost entirely
through Tier 1 and Tier 2 channels — which is why network-building
([`04-network-strategy.md`](./04-network-strategy.md)) is a portfolio-construction
activity, not a nice-to-have. Raising *quality-inbound rate* (better thesis-specific
positioning, warmer channels) is far cheaper than raising raw volume.

---

## Sensitivity — where the funnel breaks

The output (18 checks) is most sensitive to the two biggest filters: the triage ADVANCE
rate and the Data Room → IC cut. Small changes compound.

| Scenario | Change | Effect on invested (all else equal) | Fix |
|---|---|---|---|
| **Thin top-of-funnel** | Quality inbound −30% | ~13 checks — misses the 15–20 band | Reinvest in Tier 1 (operator intros, referrals) |
| **Triage too loose** | ADVANCE 18% → 28% | More founder calls, no more invested; Cam's time wasted | Hold the triage bar; WATCH is not ADVANCE |
| **Triage too tight** | ADVANCE 18% → 10% | ~10 checks — starves the funnel | Re-check for false negatives; recalibrate scorecard |
| **DD cut deepens** | Data Room → IC 30% → 20% | ~12 checks | Usually a *sourcing* signal — deals weren't as strong as triage read |
| **Higher-signal mix** | Tier 1 share of flow rises | Better conversion at every stage, fewer inbounds needed | The goal — see network strategy |

**Rule of thumb:** if the fund is under-supplied, the lever is almost always *more
Tier 1 flow*, not *lower standards*. Loosening triage produces more founder calls and
zero more investments — it just burns the scarcest resource (Cam's time) and the second
scarcest (conviction).

---

## Reconciling the funnel with reality (quarterly)

Each quarter, in the funnel review (owner: Cam), compare planned vs actual:

1. **Actual conversion rates** at each stage vs the table above → update the assumptions.
2. **Quality-inbound rate** — is on-thesis flow tracking to ~4/week? If not, which
   channel is under-producing?
3. **Pacing** — are we on track for ~6 checks/year? Ahead or behind, and why?
4. **Channel attribution** — which channels produced the deals that *advanced*, not just
   the ones that arrived? Feed this back into [`01-sourcing-channels.md`](./01-sourcing-channels.md).

The funnel is a model, not a fact. Its job is to make under-supply visible *early* —
while there is still time to fix sourcing — rather than at the end of the investment
period when the portfolio is already too small to build.

---

*Cross-references: channels that fill the top → [`01-sourcing-channels.md`](./01-sourcing-channels.md) ·
the pipeline that tracks the stages → [`02-pipeline-crm-ops.md`](./02-pipeline-crm-ops.md) ·
capital split behind the check count → [`../04-portfolio-construction/`](../04-portfolio-construction/).*
