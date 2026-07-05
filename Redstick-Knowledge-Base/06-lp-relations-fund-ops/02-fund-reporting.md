# 06.02 — Fund Reporting & Metrics

What we measure, how we mark it, and what we show LPs versus what we keep internal.
A $5M seed fund on a 10-year horizon spends most of its life with almost nothing
realized — the reporting job is to represent an unrealized, long-dated, concentrated
book **honestly and conservatively** so that when exits do arrive, the realized numbers
validate the marks rather than embarrass them.

> Canonical facts live in [`../../CLAUDE.md`](../../CLAUDE.md). Fund I is evaluated on
> **MOIC, not IRR** (`CLAUDE.md` §1). That is deliberate and it governs this document.

---

## Why MOIC, not IRR

Fund I is judged on the **multiple of invested capital**, not the internal rate of
return. Three reasons, all specific to a concentrated seed fund:

- **Power-law construction.** Returns come from a handful of outliers over a long hold.
  MOIC captures "how many times did we return the fund"; IRR punishes the long hold that
  the power law requires.
- **Small fund, lumpy cash flows.** With 15–20 checks of $100K/$250K, IRR is violently
  sensitive to the timing of a single call or distribution — noise, not signal.
- **The fund-returner bar is a multiple.** A single deal must return $5M to the fund.
  That bar is naturally expressed as MOIC, and it is how every deal's EV is underwritten
  at triage (MOIC @ cap). Reporting in the same unit keeps the whole system coherent.

IRR may be computed **internally** for cross-fund benchmarking, but it is **not** an
LP-facing headline for Fund I. Do not lead an LP letter with IRR.

---

## Fund-metrics glossary

| Metric | Full name | Formula | Reads as | Notes for Fund I |
|---|---|---|---|---|
| **TVPI** | Total Value to Paid-In | (Distributions + Residual Value) ÷ Paid-In Capital | Total value per $1 called | The headline interim metric. Combines realized + unrealized. |
| **DPI** | Distributions to Paid-In | Cumulative Distributions ÷ Paid-In Capital | Realized cash returned per $1 called | Near zero for years — normal for early seed. Honesty metric. |
| **RVPI** | Residual Value to Paid-In | Residual (unrealized) Value ÷ Paid-In Capital | Unrealized value per $1 called | TVPI = DPI + RVPI. Most of Fund I's value sits here early. |
| **MOIC** | Multiple on Invested Capital | Total Value ÷ Invested Capital | Multiple on money *invested* | **Primary return unit.** Can be gross (deal/fund) or net (to LP). |
| **Paid-In** | Paid-In / Called Capital | Capital drawn from LPs to date | Denominator for TVPI/DPI/RVPI | Includes capital for fees + investments. |
| **Invested Capital** | — | Capital actually deployed into companies | Denominator for MOIC | Excludes uncalled commitment and (for gross deal MOIC) fees. |
| **Gross MOIC** | — | Portfolio value ÷ capital invested in companies | Deal-level performance | Before fees, carry, fund expenses. |
| **Net MOIC** | — | Value to LPs ÷ capital paid in by LPs | LP take-home | After fees, carry, expenses. Always the lower number. |
| **IRR** | Internal Rate of Return | Time-weighted annualized return | Annualized % | Internal benchmarking only for Fund I; not an LP headline. |

**TVPI decomposition, always:** `TVPI = DPI + RVPI`. Early in the fund, expect
DPI ≈ 0.0x and RVPI carrying the whole TVPI. Say so plainly — a DPI of zero at year two
is the fund working to plan, not a problem.

---

## Gross vs. net — label everything

Every multiple must state whether it is **gross** (deal- or portfolio-level, before
fund economics) or **net** (to the LP, after management fee, carry, and fund expenses).

- **Gross MOIC / gross TVPI** — how the *investments* are doing. Used internally and to
  show underwriting quality.
- **Net MOIC / net TVPI / net DPI** — what the *LP* actually receives. This is the
  number LPs care about and the number Fund II gets raised on.
- Fund I nets roughly **$4.725M** of the $5.0M committed after estimated fees/expenses
  (`CLAUDE.md` §1) — the gap between gross and net is real money and we never hide it.
- **Rule:** any multiple in an LP letter is labeled gross or net on the same line. An
  unlabeled multiple is a reporting defect.

Exact fee and carry inputs to the net calculation are LPA-governed — see
[`03-fund-administration.md`](./03-fund-administration.md) — and marked `[confirm with LPA]`.

---

## Valuation policy — how we mark

Redstick marks **conservatively**. The governing principle: an early seed position is
worth what we paid until an arm's-length event proves otherwise. We would rather carry
a quiet winner at cost and surprise LPs to the upside than write up on our own optimism
and walk it back later. Marks follow a fair-value framework consistent with the LPA and
our auditor `[confirm valuation policy with LPA / auditor]`.

| Situation | How we mark | Rationale |
|---|---|---|
| No priced round, no material event | **At cost** | Default. Early SAFE/note value is unobservable; cost is the honest floor. |
| New priced round (arm's-length, new lead) | **At the new round price** | A real third party set the price. Mark to it, net of any structure. |
| SAFE/note converts in a priced round | Mark to conversion value at round terms | The cap/discount crystallizes into equity at an observable price. |
| Material adverse event (down round, key-person loss, missed milestone, cash-out risk) | **Write down** to supportable value; to zero if impaired | Bad news is marked immediately, not deferred to the next quarter. |
| Insider-only / SAFE-extension round (no new lead) | Hold at cost unless clearly impaired | An inside round is not an arm's-length price; do not write up on it. |
| Distressed / wind-down | **Write to zero** (or recoverable value) | Recognize the loss when known. A ~2% TVPI drag per $100K, ~5% per $250K. |
| Public/liquid milestone (rare at this stage) | Mark to market, less any lock-up discount | Observable price governs. |

**Conservatism rules that override the table:**

- **Do not write up on a SAFE cap.** A high cap on a new SAFE is not a validated price.
- **Down rounds are marked immediately.** Never smooth a markdown across quarters.
- **Every mark cites its basis** — as-of date, the event (round/close/impairment), the
  price, and the FX rate for CAD positions.
- **When in doubt, hold at cost.** Optimism is not an observable input.

---

## USD / CAD normalization

The fund's books and all LP reporting are in **USD**. Many portfolio companies raise and
report in **CAD**. Reporting discipline:

- **Report currency: USD.** Every LP-facing metric is USD.
- **Every figure is labeled** `USD` or `CAD` at the point of use — no bare dollar signs.
- **State the FX rate** used for each report, as-of the reporting date, on the cover of
  the pack. Example convention: `1 USD = 1.3600 CAD [illustrative rate — set to the
  actual quarter-end rate]`.
- **CAD positions are held on the books at cost in USD at the entry-date rate**, and
  **revalued at the reporting-date rate** for current value. The FX component of any
  change is disclosed separately from the operating/valuation component so LPs can see
  what moved the position vs. what moved the currency.
- **CAD-funding LPs** (e.g. FCC) are handled per their subscription docs; the fund still
  reports its consolidated book in USD `[confirm FX and funding convention with LPA /
  side letters]`.

---

## Reporting calendar

| Report | Frequency | Timing | Audience | Prepared by |
|---|---|---|---|---|
| Quarterly LP letter + metrics pack | Quarterly | Within 45 days of quarter-end | All LPs | Cam (Olli drafts) |
| Portfolio marks refresh | Quarterly (monthly for material events) | Quarter-end | Internal → feeds LP pack | Cam |
| Annual audited financials | Annual | Post-fiscal-year, per audit timeline | All LPs | Fund admin + auditor |
| Annual LP meeting deck | Annual | Q1, on prior FY | All LPs | Cam + Shane |
| Year-end investor newsletter | Annual | December | All LPs + network | Cam (Olli drafts) |
| K-1 / tax reporting | Annual | Per tax-prep timeline `[confirm]` | All LPs | Tax provider |
| Strategic-LP policy metrics | Quarterly + annual summary | With the pack | FCC, CFIN | Olli assembles |

Full mechanics and provider list in [`03-fund-administration.md`](./03-fund-administration.md).

---

## LP-facing vs. internal-only

| Metric / artifact | LP-facing | Internal-only |
|---|---|---|
| TVPI, DPI, RVPI (net) | ✅ | ✅ |
| MOIC — blended gross | ✅ | ✅ |
| MOIC — net to LP | ✅ | ✅ |
| Per-company marks (named, with consent) | ✅ (highlights) | ✅ (full) |
| Deployment / reserves / dry powder | ✅ | ✅ |
| Strategic-LP policy metrics | ✅ (to strategic LPs) | ✅ |
| Deal-level EV models / triage MOICs | ❌ | ✅ |
| Per-company fail-probability estimates | ❌ | ✅ |
| Internal IRR (benchmarking) | ❌ | ✅ |
| Watch-list internal notes / founder-confidential detail | ❌ | ✅ |
| Reserve/follow-on decision models | ❌ | ✅ |

Guiding line: LPs get **fund-level truth and consented company highlights**;
underwriting internals, unconsented company detail, and probabilistic deal models stay
in the shop. When unsure, default to conservative disclosure and check with Cam.
