# 07.01 — Fund Structure

How a fund like Redstick Ventures Fund I is put together as a set of legal entities,
who the parties are, and who has authority to commit the fund's capital. This is the
map an emerging manager needs to explain the fund to an LP, brief counsel efficiently,
and know which entity signs what.

> **⚠️ Not legal advice.** This document describes how emerging-manager venture funds
> are *typically* structured. It does **not** state Redstick's actual legal facts.
> Every item marked `[confirm with LPA]` or `[confirm with counsel]` must be filled in
> from the fund's executed Limited Partnership Agreement and by fund counsel. Do not
> represent any of the generic descriptions below to an LP or regulator as Redstick's
> settled structure until confirmed.

> Canonical fund facts (size, checks, thesis) live in
> [`../../CLAUDE.md`](../../CLAUDE.md) and win over anything here.

---

## 1. The three-entity pattern (typical)

Most venture funds separate the *pool of capital*, the *decision-maker*, and the
*service business* into three distinct legal entities. This is deliberate: it isolates
liability, cleanly separates LP money from GP money, and lets fee and carry economics
flow to the right place.

| Entity | Common form | What it is | Who owns it |
|---|---|---|---|
| **Fund vehicle** | Limited Partnership (LP) — sometimes LLLP `[confirm with LPA]` | The pool that holds LP capital and makes the investments. LPs are limited partners here. | LPs (limited partners) + the GP entity (general partner) |
| **General Partner (GP) entity** | LLC or LP `[confirm with LPA]` | The legal general partner of the fund vehicle. Holds the **carried interest**, bears unlimited liability for the fund, and makes/authorizes investment decisions. | The principals (Cam, and per the LPA any other principals) `[confirm with LPA]` |
| **Management company** | LLC `[confirm with counsel]` | The operating business. Employs the team, pays expenses, and receives the **management fee**. Contracts with the fund via a management agreement. | The principals |

> **Why the split matters for Redstick:** even at $5M, keeping the GP entity (which
> bears fund liability and holds carry) separate from the management company (which runs
> payroll and operations) is standard and worth doing. `[confirm with counsel]` whether
> a single combined entity is acceptable at this size, or whether the three-entity
> pattern is required by the LPA / investors.

---

## 2. Economics as concepts (numbers `[confirm with LPA]`)

These are the standard economic terms. **Do not assume Redstick's actual figures** —
they live in the executed LPA.

| Term | What it means | Redstick value |
|---|---|---|
| **Fund size / commitments** | Total LP capital committed. | **$5.0M** (per CLAUDE.md; ~$4.725M net) |
| **Management fee** | Annual % of commitments (or NAV) paid to the management company to run the fund; funds operations and salary. Often ~2%/yr over the investment period, sometimes stepping down. | `[confirm with LPA]` % and basis |
| **Carried interest** | The GP's share of profits above return of capital (and any hurdle). Often ~20%. | `[confirm with LPA]` % |
| **Hurdle / preferred return** | Minimum LP return before carry accrues, if any. Many small venture funds have none. | `[confirm with LPA]` |
| **GP commitment** | The GP's own capital into the fund, aligning incentives. Often 1–2% of fund size. | `[confirm with LPA]` |
| **Fund term** | Life of the fund (e.g. 10 years + extensions), with an investment period (e.g. first 3–5 years). | `[confirm with LPA]` |
| **Distribution waterfall** | Order in which proceeds flow: return of capital → preferred return (if any) → carry split. | `[confirm with LPA]` |

> Redstick evaluates Fund I on **MOIC**, not IRR (CLAUDE.md). That is the *reporting*
> lens; it does not change the *legal* waterfall, which is whatever the LPA states.
> Keep the two separate when talking to LPs.

---

## 3. US ↔ Canada cross-border considerations (high level)

Redstick is North America (US + Canada); founders and LPs may sit on either side of the
border, and deals are frequently in CAD. Cross-border structure is where an emerging
manager most needs counsel — mistakes here are expensive and hard to unwind.

**Framed generically — every point is `[confirm with counsel / tax advisor]`:**

- **Fund domicile & vehicle choice.** A US-domiciled LP, a Canadian LP, or a parallel /
  feeder structure each have different tax and filing consequences for the two investor
  populations. LP vs. LLLP is one axis; the domicile is the bigger one. `[confirm]`
- **Blocker entities.** Where US-taxable and Canadian-taxable investors are mixed, or
  where certain investments would create adverse pass-through consequences (e.g. UBTI
  for US tax-exempt LPs, or FAPI/PFIC issues for Canadian investors in US entities), a
  **blocker corporation** is sometimes inserted so income is taxed at the entity level
  instead of passing through. Whether Redstick needs any blocker is a `[confirm with
  counsel]` question driven by the LP base. Do not assume one is or isn't needed.
- **Withholding tax.** Cross-border distributions can trigger withholding (e.g. US
  withholding on payments to non-US persons, Canadian withholding on payments to
  non-residents), potentially reduced by the Canada–US tax treaty. Withholding rates,
  treaty eligibility, and required forms (e.g. W-8 series / NR forms) are `[confirm with
  tax advisor]`.
- **Currency.** Fund reporting is **USD** (CLAUDE.md); many deals are **CAD**. FX policy,
  the rate source, and timing of conversion for reporting and distributions should be
  written down. This is an operational choice, not a legal fact — but be consistent and
  disclose it to LPs.
- **Investor eligibility across borders.** The offering exemption relied on differs by
  investor's jurisdiction (see [`02-regulatory.md`](./02-regulatory.md)). A single LP
  close may rely on different exemptions for US vs. Canadian investors. `[confirm with
  counsel]`

> **Rule of thumb:** any structure that touches both countries' tax systems is a
> counsel-and-tax-advisor decision *before* the money moves, not after.

---

## 4. The parties and their roles

| Party | Who | Role |
|---|---|---|
| **General Partner** | GP entity, principals **Cam Crowder** (GP) — with co-founder **Shane Larisey** | Makes and authorizes investments; bears fund liability; holds carry; owes fiduciary duties to LPs. |
| **Limited Partners** | The fund's investors | Provide capital; limited liability; no role in day-to-day investment decisions; receive reporting and distributions. |
| **Fund administrator** | Third-party admin `[confirm — engaged? which?]` | Keeps the books, calculates NAV, processes capital calls / distributions, maintains the register of LPs. Right-sized: even small funds benefit from an admin over doing it in a spreadsheet. |
| **Auditor** | Third-party audit firm `[confirm — required by LPA?]` | Annual financial statement audit if required by the LPA or investors. `[confirm with LPA]` whether audit is mandatory at this fund size. |
| **Fund counsel** | Law firm `[confirm]` | Drafts/maintains the LPA and subscription docs, advises on exemptions, cross-border, and conflicts. The first call for any novel situation. |
| **Tax advisor** | Accounting firm `[confirm]` | Fund tax returns, K-1s / T-slips to LPs, cross-border withholding, blocker analysis. |
| **AI EA** | **Olli** (`olli@redstickvc.com`) | Operational coordination — intake, scheduling, reporting logistics. **No decision authority.** Not a party to any legal document. |

---

## 5. Decision authority — who can approve an investment

Right-sized for a two-person emerging manager: the **Investment Committee (IC) is the
GP.** There is no need for a large IC or an outside investment committee at $5M.

| Decision | Authority | Notes |
|---|---|---|
| **New investment ($100K or $250K)** | IC approval — **Cam as GP**, with Shane's diligence input | Whether IC approval requires one GP or unanimity of two GPs is a governance choice. **Recommended: both principals sign off** where two principals exist, so no single person commits fund capital alone. `[confirm with LPA]` for the formal requirement. |
| **Follow-on / reserve deployment** | Same IC | Subject to reserve policy in [`../04-portfolio-construction/`](../04-portfolio-construction/). |
| **SPV / co-investment allocation** | Same IC + conflicts check | Must clear the allocation rules in [`03-conflicts-policy.md`](./03-conflicts-policy.md). |
| **Anything triggering a conflict** | IC **minus** the conflicted principal (recusal) | See conflicts policy, Section on disclosure & recusal. |
| **Capital calls / distributions** | GP authorizes; admin executes | Per LPA mechanics. `[confirm with LPA]` |
| **Amending the LPA / fund terms** | GP + LP consent thresholds | Consent thresholds are `[confirm with LPA]`. |

**Documentation discipline (right-sized):** every investment decision is recorded — the
IC memo (per the diligence process) plus a short written approval noting who approved,
the amount, the instrument, and any conflict cleared. A one-paragraph record is enough
at this scale; the point is that a decision is *traceable*, not that it is bureaucratic.

---

## 6. Fund-structure checklist

Use this when standing up the fund, onboarding a new LP class, or briefing counsel.

**Entities**
- [ ] Fund vehicle entity formed; type and domicile confirmed `[confirm with LPA]`
- [ ] GP entity formed; holds carry; bears general-partner liability `[confirm]`
- [ ] Management company formed; management agreement with the fund in place `[confirm]`
- [ ] GP commitment funded per the LPA `[confirm with LPA]`

**Documents**
- [ ] Executed LPA on file; a plain-language summary exists for the team
- [ ] Subscription documents / investor questionnaire in place (ties to KYC — doc 02)
- [ ] Management agreement and any advisory agreements executed
- [ ] Distribution waterfall understood and documented

**Economics (confirm, don't assume)**
- [ ] Management fee % and basis confirmed `[confirm with LPA]`
- [ ] Carried interest % and any hurdle confirmed `[confirm with LPA]`
- [ ] Fund term, investment period, and extension mechanics confirmed `[confirm with LPA]`

**Cross-border**
- [ ] LP base mapped by tax jurisdiction (US / Canada / other)
- [ ] Blocker / feeder need assessed with counsel `[confirm with counsel]`
- [ ] Withholding and treaty position confirmed with tax advisor `[confirm]`
- [ ] FX / reporting-currency policy written down (reporting is USD)

**Service providers**
- [ ] Fund administrator engaged (or explicit decision to self-administer) `[confirm]`
- [ ] Auditor engaged if audit required `[confirm with LPA]`
- [ ] Fund counsel and tax advisor of record identified

**Authority**
- [ ] IC composition and approval rule documented (recommended: both principals sign)
- [ ] Investment-approval record template in use (who / amount / instrument / conflicts)
- [ ] Recusal procedure defined for conflicted decisions (see doc 03)

---

## Related

- Regulatory obligations that sit on top of this structure:
  [`02-regulatory.md`](./02-regulatory.md)
- Conflicts that this authority structure must manage:
  [`03-conflicts-policy.md`](./03-conflicts-policy.md)
- LP-facing operations of this structure:
  [`../06-lp-relations-fund-ops/`](../06-lp-relations-fund-ops/)
- Portfolio-construction rules that bound deployment decisions:
  [`../04-portfolio-construction/`](../04-portfolio-construction/)
