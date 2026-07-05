# 06.03 — Fund Administration

The plumbing. Capital calls, distributions, the waterfall, audit and tax cadence,
banking, subscription docs, recordkeeping, and the service providers who make a
two-person GP team operate like an institution. None of this is glamorous, and all of
it is what a returning LP quietly checks before writing a Fund II commitment.

> **Read this first:** the binding numbers for fee, carry, hurdle, and waterfall live in
> the **Limited Partnership Agreement (LPA)**, not this document. Everything below that
> is not fixed in [`../../CLAUDE.md`](../../CLAUDE.md) is marked `[confirm with LPA/GP]`
> and is **illustrative** — used to explain the mechanics, not to assert a term. Where
> this doc and the LPA disagree, the **LPA wins**.

---

## Capital calls — mechanics

Fund I is a committed-capital vehicle: LPs commit up front and the fund **draws** capital
as it deploys, rather than taking the full $5.0M on day one.

- **Trigger.** Capital is called to fund new investments, reserves, management fee, and
  fund expenses. The GP determines timing against deployment pace (target 15–20 companies).
- **Notice.** A written call notice goes to each LP stating: total amount called (USD),
  that LP's **pro-rata share** of the call, cumulative called-to-date, wire instructions,
  and the **due date**. Notice period per the LPA `[confirm — typically ~10 business days]`.
- **Pro-rata basis.** Each LP is called on their share of committed capital. Called %
  moves in lockstep across all LPs unless a side letter says otherwise `[confirm]`.
- **Funding.** LPs wire to the fund's capital account (banking below). Fund admin
  reconciles receipts; the GP confirms.
- **Default remedy.** An LP who fails to fund a call is subject to the LPA's default
  provisions `[confirm with LPA]` — Redstick's small, relationship-driven LP base makes
  this rare, but the mechanism exists.
- **CAD-committed LPs.** Calls are denominated per the subscription doc; the fund's books
  consolidate in USD at the stated FX rate `[confirm funding/FX convention with LPA]`.

**Illustrative call sequence (mechanics only, not a schedule):**

| Call | Purpose | Called this call (USD) | Cumulative called | % of commitment |
|---|---|---|---|---|
| 1 | Initial: fee + first checks | $[  ]M | $[  ]M | [ ]% |
| 2 | Two new seed checks + reserves | $[  ]M | $[  ]M | [ ]% |
| … | As deployment requires | … | up to $5.0M | up to 100% |

---

## Distributions & the waterfall (illustrative)

When a portfolio company exits (acquisition, secondary, or — rarely at this stage —
IPO), proceeds are distributed to LPs through the LPA's **distribution waterfall**. The
structure below is a **standard 2/20-style illustration** to explain the mechanics — it
is **not** an assertion of Fund I's actual terms. **Confirm every number on the LPA.**

**Illustrative waterfall (confirm all tiers with LPA):**

| Tier | Who gets paid | Illustrative terms `[confirm with LPA]` |
|---|---|---|
| 1. Return of capital | LPs | 100% to LPs until paid-in capital returned |
| 2. Preferred return / hurdle | LPs | Hurdle if any `[confirm — many small seed funds have none]` |
| 3. GP catch-up | GP | Catch-up if a hurdle exists `[confirm]` |
| 4. Carried-interest split | GP / LPs | Carry to GP, remainder to LPs `[confirm — illustratively 20/80]` |

**Illustrative economics (NOT confirmed — placeholders for the LPA):**

| Term | Illustrative value | Status |
|---|---|---|
| Management fee | ~2%/yr of committed (illustrative) | `[confirm with LPA]` — implied net ~$4.725M suggests fees/expenses ~$275K over life; do **not** back-solve a fee from this |
| Carried interest | 20% (illustrative) | `[confirm with LPA]` |
| Hurdle / preferred return | Possibly none | `[confirm with LPA]` |
| Fee basis (committed vs. invested) | Committed (illustrative) | `[confirm with LPA]` |
| Fund term | ~10 yrs + extensions (illustrative) | `[confirm with LPA]` |
| Recycling of proceeds | Possibly permitted | `[confirm with LPA]` |

> The **only** fixed capital facts are from `CLAUDE.md`: **$5.0M committed, ~$4.725M
> net**. That ~$275K gap covers fees and fund expenses over the fund's life but does
> **not** by itself fix the fee rate, basis, or carry — those are LPA terms. Never
> present the illustrative 2/20 as Redstick's actual terms in an LP-facing document.

---

## Fund admin, accounting, audit & tax cadence

| Activity | Frequency | Owner | Notes |
|---|---|---|---|
| Bookkeeping / capital-account maintenance | Ongoing / monthly | Fund admin | Per-LP capital accounts, called/distributed tracking |
| Bank + investment reconciliation | Monthly | Fund admin | Cash, wires, holdings vs. cap table |
| Portfolio marks | Quarterly (monthly for material events) | Cam | Per valuation policy in [`02-fund-reporting.md`](./02-fund-reporting.md) |
| Quarterly LP reporting pack | Quarterly | Fund admin + Cam | Feeds the LP letter |
| Annual financial statements | Annual | Fund admin | Basis per LPA `[confirm GAAP/ASPE/fair-value]` |
| Audit | Annual `[confirm if required by LPA]` | External auditor | Many sub-$10M funds negotiate audit scope — confirm |
| Tax returns + LP K-1s (or CAD equivalents) | Annual | Tax provider | Cross-border US/CAD complexity — see below |
| Regulatory / compliance filings | Per calendar | See [`../07-governance-compliance/`](../07-governance-compliance/) | Fund ops executes what governance defines |

**Cross-border note.** Redstick invests across the US and Canada from a USD-reporting
fund. US and Canadian LPs may have different tax reporting (K-1 vs. Canadian slips), and
CAD-denominated investments create FX and potential withholding considerations. This is
handled by the tax provider — **confirm entity structure and per-LP tax reporting with
the LPA, fund counsel, and tax provider** `[confirm]`. Do not improvise tax treatment.

---

## Banking

- **Fund operating/capital account** — receives capital calls, pays fees/expenses,
  funds investments. USD account is the fund's book of record.
- **CAD handling** — a CAD account or FX conversion facility for Canadian deals;
  conversions booked at the transaction-date rate, disclosed against the reporting-date
  rate `[confirm banking setup with GP]`.
- **Controls** — dual review on outbound wires (GP + fund admin), documented wire
  instructions, and verification of any new/changed payee out-of-band (anti-fraud).
- **Signatories** — per the LPA / fund governance `[confirm]`.

---

## Cap table, subscription & closing documents

- **LPA** — the governing document. Binds fee, carry, waterfall, term, notice periods,
  LP rights. The source of truth this whole doc defers to.
- **Subscription agreements** — each LP's commitment, representations, and any
  side-letter terms (e.g. FCC/CFIN strategic reporting rights).
- **Side letters** — LP-specific terms; strategic LPs (FCC, CFIN) may carry
  reporting/mandate obligations. Track these so reporting in
  [`01-lp-comms.md`](./01-lp-comms.md) matches what was promised.
- **Investment closing docs** — per portfolio company: executed SAFE/note/priced-round
  docs, board/observer rights, pro-rata/MFN/info-rights terms, wire confirmation.
- **Fund cap table (LP-side)** — commitments, called-to-date, distributed-to-date,
  ownership % of the fund, per LP. Maintained by fund admin, reconciled quarterly.
- **Portfolio cap tables (company-side)** — Redstick's position in each company;
  updated on each round and used for marks and dilution tracking.

---

## Recordkeeping

- **Single source of record is this repo + the fund admin's system.** Notion mirrors for
  navigation; the LPA and executed docs are the legal record.
- **Retain:** all LP subscription/side-letter docs, call and distribution notices,
  quarterly packs, audited financials, tax filings, board consents, and executed
  investment docs — for the life of the fund plus the LPA-required tail `[confirm
  retention period]`.
- **Access & confidentiality:** LP-identifying and founder-confidential material is
  need-to-know. Internal-only vs. LP-facing split is defined in
  [`02-fund-reporting.md`](./02-fund-reporting.md).
- **Audit trail:** every mark, call, and distribution ties back to a dated source
  document. If it isn't documented, it didn't happen.

---

## Key service providers checklist

A two-person GP team runs institutional-grade because these seats are filled and named.
Confirm each provider and contact with the GP `[confirm with GP]`.

| Function | Provider | Status | What they do |
|---|---|---|---|
| **Fund administration** | [  ] | `[confirm]` | Capital accounts, calls/distributions, NAV, LP reporting pack |
| **Fund accounting** | [  ] (often bundled with admin) | `[confirm]` | Bookkeeping, financial statements, reconciliations |
| **Legal / fund counsel** | [  ] | `[confirm]` | LPA, subscriptions, side letters, regulatory, deal docs |
| **Audit** | [  ] | `[confirm if required]` | Annual audited financials |
| **Tax** | [  ] | `[confirm]` | Fund + LP tax returns, K-1s / CAD slips, cross-border |
| **Banking** | [  ] | `[confirm]` | USD capital account; CAD/FX handling |
| **Compliance / regulatory** | [  ] | `[confirm]` | Filings per [`../07-governance-compliance/`](../07-governance-compliance/) |
| **Insurance (GP/mgmt liability)** | [  ] | `[confirm]` | E&O / management liability if carried |

**Onboarding rule:** before the first capital call, confirm fund admin, counsel, and
banking are live. Before the first annual reporting cycle, confirm audit (if required)
and tax. Log each provider, contact, and engagement terms with the GP — everything on
this page that isn't in `CLAUDE.md` is `[confirm with LPA/GP]` until verified.
