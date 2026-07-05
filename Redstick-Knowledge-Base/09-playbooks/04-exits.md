# 09.04 — Exits

The playbook for when a position becomes liquid — or dies. This is where MOIC stops
being a projection and becomes a realized number. For a concentrated $5M seed fund,
a small number of exits determine the entire fund outcome, and the fund-returner math
is the lens on every one of them.

> Canonical facts live in [`../../CLAUDE.md`](../../CLAUDE.md). Fund I is $5M,
> evaluated on **MOIC**, and the **fund-returner bar is a single deal returning $5M**.
> Distributions and waterfall specifics are read off the LPA — see
> [`../06-lp-relations-fund-ops/`](../06-lp-relations-fund-ops/), and mark anything
> not fixed in `CLAUDE.md` as `[confirm with LPA/GP]`.

---

## The one-screen version

- **The whole fund rides on the right tail.** Power-law construction means one or two
  fund-returners drive the result; most positions return little or zero. Exit strategy
  is about maximizing the winners, not salvaging the losers.
- **A fund-returner returns $5M on one deal.** *Illustratively*, that is roughly a
  ~$221M exit on a $250K check entered at a $6M cap, or ~$551M on a $100K check at the
  same cap (from the [deal-triage skill](../../skills/deal-triage/SKILL.md)) — after
  dilution to ~40–54% of entry ownership. That bar frames whether an early exit offer
  is "great" or is capping our upside.
- **Liquidation preferences can gut a headline number.** An acquihire or modest sale
  can look like a win and return <1x after the preference stack pays out ahead of us.
  Always model the waterfall, never the press release.
- **Write-offs are a process, not a shrug.** Every shutdown gets a lessons-learned
  capture. A failure we learn nothing from is the only unforgivable one.

---

## Exit types and how they map to MOIC

| Exit type | Frequency (seed) | Typical MOIC to us | Key caveat |
|---|---|---|---|
| **Write-off / shutdown** | Common (≥20% floor) | 0x | Capture the lesson; take the tax treatment |
| **Acquihire** | Common | 0x–1.5x | Liq-pref stack often eats the common upside |
| **Secondary sale** | Occasional | Varies — we set it | Trades upside for certainty; decision framework below |
| **Strategic M&A** | The realistic win | 3x–fund-returner | Multiple on ARR; where most real MOIC comes from |
| **IPO** | Rare at our stage | Fund-returner class | Long hold, lockups; the exception, not the plan |

**The acquihire caveat (from the SKILL):** in an acquihire or low-value sale, a
liquidation-preference stack pays senior investors first. A $250K check can return a
fraction of cost even when the founders and press call it a "successful exit." Model
MOIC *after* the preference waterfall — the headline price is not our proceeds.

---

## The fund-returner math on every exit

Run this before reacting to any offer. It answers one question: is this outcome
material to the fund, or a rounding error?

```
Our proceeds  = (our diluted ownership × exit equity value)  −  senior preferences ahead of us
Our MOIC      = proceeds ÷ our check ($100K or $250K)
Fund impact   = proceeds ÷ $5M          (share of a full fund return)
Fund-returner = a single deal returning $5M in proceeds
```

- Diluted ownership: base retention ×0.64 of entry; strong/fund-returner ×0.544
  (per the SKILL dilution model).
- Tie exit equity value to ARR × multiple; state which ARR (contracted vs recognized).
- If proceeds < the check, it is a **loss** regardless of the transaction's label.

---

## Secondary-sale decision framework — sell early or hold?

Secondaries are the one exit where *we* choose the timing. Selling early converts
paper into cash and de-risks; holding preserves the right-tail that the fund depends
on. The default for a power-law fund is **hold the potential fund-returners** — but
there are real reasons to sell.

| Sell (take the secondary) when… | Hold when… |
|---|---|
| The position can no longer plausibly return the fund ($5M) | It is still on a fund-returner path |
| DPI is needed to prove the model for Fund II and liquidity is offered at a fair price | Early exit would cap the very outcome the fund is built on |
| Conviction has fallen but the mark is still high (sell into strength) | Conviction is intact or rising |
| Concentration/risk in one name is uncomfortable and a clean price exists | The buyer's price is below our own view of value |
| A credible buyer offers a price at/above our honest intrinsic view | No fair price; forced sellers get bad prices |

**Discipline:** never sell a genuine fund-returner early to manufacture DPI. One
company returning $5M matters more than smoothing the interim numbers. Sell the
positions that have stopped being winners, not the ones that still could be.

---

## Managing the liquidation-preference stack

Before treating any M&A or acquihire as a win, reconstruct the waterfall:

1. **Pull the current cap table and all preference terms** — 1x/participating/senior,
   by round. A later, larger round often sits *senior* to us.
2. **Order the stack:** senior preferences pay first, then pari-passu, then common.
   Our SAFE/note converts to a class — know which.
3. **Compute proceeds at the offer price** *after* everyone senior is paid.
4. **Compare to the check.** Below cost = a loss dressed as an exit.
5. **Check the participation feature** — participating preferred double-dips (pref +
   pro-rata of the remainder), further compressing common/junior proceeds.

> *Illustrative only:* a company sells for $40M with $35M of senior 1x-participating
> preferences ahead of us. The residual to junior holders is thin; a $250K position
> could return well under 1x despite a $40M headline. Model it; don't celebrate it.
> (Worked example, not a real portfolio outcome.)

---

## Exit-decision table

| Situation | Default action | Watch-out |
|---|---|---|
| Strategic M&A, price ≥ our intrinsic view | Support the sale; model waterfall | Preference stack; earn-out risk to proceeds |
| Strategic M&A, price < our view, company healthy | Advise holding if founders aligned | We don't control the vote — influence only |
| Acquihire, thin proceeds to us | Model waterfall first; likely ~0x–1x | "Successful exit" label ≠ our return |
| Secondary offered, still a fund-returner | Hold (default) | Don't sell the winner to make DPI |
| Secondary offered, thesis broken | Sell into strength | Fair price vs. forced-seller discount |
| IPO path | Hold through lockup; plan distribution | Long hold, volatility, lockup timing |
| No path, cash gone | Write-off (below) | Take the lesson and the tax treatment |

---

## Distribution mechanics to LPs

Realized proceeds flow to LPs per the LPA — this playbook frames the mechanics; the
binding numbers live in
[`../06-lp-relations-fund-ops/`](../06-lp-relations-fund-ops/) and the LPA
(`[confirm with LPA/GP]`).

- **Realize, then distribute.** On close of an exit, proceeds are received into the
  fund, then distributed per the waterfall (return of capital → preferred return →
  carry split — exact terms on the LPA).
- **Cash vs. in-kind.** Public/liquid stock may be distributed in kind; private cash
  exits distribute cash. State which in the notice.
- **Update the metrics.** A realized exit moves DPI (real cash returned) and reduces
  RVPI (unrealized). MOIC on that position becomes final. Refresh the fund pack in
  [`../06-lp-relations-fund-ops/02-fund-reporting.md`](../06-lp-relations-fund-ops/02-fund-reporting.md).
- **Communicate it** in the quarterly letter and a distribution notice — the number,
  the source, and the impact on fund metrics. Normalize CAD proceeds to USD at the
  stated FX rate. Flag strategic-LP relevance (FCC/CFIN) where the exit is a policy
  win (Canadian company scaled, jobs, clean-tech outcome).

---

## Write-off / shutdown process

A write-off is the terminal state for ≥20% of positions by design. Run it cleanly.

### Write-off checklist

- [ ] Confirm the company is genuinely done (no bridge, no buyer, cash gone) —
      verified, not assumed
- [ ] Founder conversation: dignified close; offer help where we can (references,
      next-startup support — founders are long relationships)
- [ ] Mark the position to **$0** on the Portfolio Snapshot promptly — no lingering
      dead marks inflating TVPI
- [ ] Record the realized loss; note the TVPI drag (2% @ $100K, 5% @ $250K)
- [ ] Capture tax treatment / worthless-security documentation with fund admin
      (`[confirm with LPA/GP]`)
- [ ] Reflect the impairment honestly in the next quarterly LP letter — never buried
- [ ] File the deal docs and final cap table; close the Drive folder
- [ ] **Lessons-learned capture** against the memo of record (below)

### Lessons-learned capture (calibration culture)

Every write-off is post-mortemed against the [memo of record](./01-first-90-days.md)
written at close, per [`../../operating-cadence.md`](../../operating-cadence.md):

- **Was this failure in our bear case at close?** If yes, we underwrote it correctly
  and the variance played out — that is fine. If no, *why did we miss it?*
- **Which lens over-scored?** Founder / Market / Tech / Unit-econ / Terms — where was
  our judgment wrong, and does it recur across other misses?
- **Did influence-not-control cost us?** Would different terms have changed the
  outcome, or was the company simply always going to fail?
- **One-line thesis for the record:** what we believed, what actually happened, and
  what it changes about the *next* underwrite.

A write-off that teaches the next investment is paid tuition. A write-off we learn
nothing from is the only kind we cannot afford.

---

## How exits close the loop

```
Exit / write-off ──► realized MOIC + DPI ──► fund reporting (06) ──► LP distribution + letter
        │                                          │
        └──► lessons-learned vs. memo of record ──►┴──► next underwrite (03-diligence) sharper
```

The exit is where the fund is finally graded — and where the calibration culture pays
off, by making every outcome, win or loss, an input to the next decision.
