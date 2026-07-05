# 07.02 — Regulatory & Compliance

Right-sized compliance for a $5M emerging-manager venture fund operating across the US
and Canada. The goal is simple: raise and run the fund inside the exemptions it relies
on, treat LP and founder data responsibly, and never blow an offering exemption through
a careless marketing move. This is a discipline, not a department.

> **⚠️ Not legal advice.** Securities regulation is jurisdiction-specific and
> fact-specific. This document explains *concepts* and gives a *checklist*; it does not
> tell you which exemption Redstick actually relies on, what it has actually filed, or
> who its regulator of record is. Every item marked `[confirm with counsel]` must be
> confirmed with fund counsel before acting. **When in doubt, ask counsel — always.**

> Canonical fund facts live in [`../../CLAUDE.md`](../../CLAUDE.md).

---

## 1. The core idea: a private, exempt offering

Redstick does not register a public securities offering. It sells fund interests
privately under **exemptions** that are available only if the fund stays within their
conditions. Break a condition and the exemption can fall away — which is the single
most expensive compliance mistake a small fund can make.

Two things follow from relying on exemptions:

1. **Who you can sell to is restricted** (accredited / eligible investors — Section 2).
2. **How you can market is restricted** (general-solicitation caution — Section 4).

Both differ by country, and Redstick touches both. `[confirm with counsel]` which
specific exemptions the fund relies on in each jurisdiction.

---

## 2. Accredited-investor & exempt-offering concepts

Generic explanation. **Do not treat any threshold below as Redstick's confirmed
standard** — confirm the actual exemptions and current dollar/asset tests with counsel.

### United States (concepts)

| Concept | What it means (generic) |
|---|---|
| **Reg D — Rule 506(b)** | Common private-placement exemption. Allows raising from **accredited investors** (and a limited number of sophisticated non-accredited investors) **without general solicitation**. Relationship-based fundraising. |
| **Reg D — Rule 506(c)** | Permits **general solicitation** (public marketing) **but requires verifying** that every investor is accredited — a higher bar than self-certification. Different trade-off. |
| **Accredited investor** | Individuals meeting income/net-worth (or certain professional) tests, and qualifying entities. The exact tests are `[confirm with counsel]` and change over time. |
| **Form D** | A notice filing with the SEC (and often state "blue sky" notice filings) after the first sale. Timing matters. `[confirm with counsel]` |

### Canada (concepts)

| Concept | What it means (generic) |
|---|---|
| **Accredited Investor exemption** (NI 45-106) | Sales to investors meeting income/financial-asset/net-asset tests, or qualifying entities. Canadian equivalents to the US accredited concept, with different thresholds. `[confirm with counsel]` |
| **Offering Memorandum (OM) exemption** | Allows sales to a broader investor set if a prescribed-form OM (with audited financials and a right of action for misrepresentation) is delivered. More disclosure obligation. Availability varies by province. `[confirm with counsel]` |
| **Report of exempt distribution** (Form 45-106F1) | Filing with the relevant provincial securities regulator after an exempt distribution, typically within a set number of days. `[confirm with counsel]` |
| **Provincial variation** | Exemptions and filings are administered **province by province**; an LP's province of residence matters. `[confirm with counsel]` |

> **Cross-border reality:** a single closing may rely on a US exemption for US LPs and a
> Canadian provincial exemption for Canadian LPs — simultaneously. Map every prospective
> LP to a jurisdiction *before* accepting their subscription. See cross-border notes in
> [`01-fund-structure.md`](./01-fund-structure.md).

---

## 3. KYC / AML on LPs

Even a small fund must know who its investors are and where their money comes from.
Right-sized means real but proportionate — a documented process, not a compliance bank's
apparatus.

**At each subscription, collect and retain:**
- [ ] Verified **identity** of the investor (individual or entity + beneficial owners)
- [ ] **Accreditation / eligibility** evidence appropriate to the exemption relied on
- [ ] **Source-of-funds** comfort proportionate to the investor and amount
- [ ] Sanctions / watchlist screening appropriate to jurisdiction `[confirm with counsel]`
- [ ] Completed **subscription documents and investor questionnaire** (ties to doc 01)
- [ ] Tax forms for cross-border withholding (e.g. W-8 series / Canadian equivalents) `[confirm]`

**Retention & ownership.** Keep KYC records for the period counsel specifies `[confirm]`.
Owner: **Cam**, supported by the fund administrator where engaged. Olli may *coordinate
collection* (chasing documents, scheduling) but performs no eligibility determination.

> **Red line:** never accept capital before the investor's eligibility and identity are
> documented. A subscription that jumps the KYC step is a compliance incident.

---

## 4. Marketing & general-solicitation caution

This is where a small fund most easily trips. The rules turn on whether the fund's
offering permits **general solicitation** — and under a no-general-solicitation
exemption (like US Rule 506(b)), public marketing of the *offering* can destroy the
exemption.

**Safe defaults until counsel says otherwise:**
- [ ] **Assume the offering is NOT generally solicited** unless counsel has confirmed the
      fund is using a general-solicitation exemption (e.g. 506(c) with verification).
      `[confirm with counsel]`
- [ ] **Do not publicly advertise the fundraise** — no "we're raising Fund I, DM to
      invest" posts, no open webinars pitching fund interests, no press about open
      subscription terms — without a counsel-cleared basis.
- [ ] **Separate brand-building from fundraising.** Talking publicly about the *thesis*,
      the *market*, and *portfolio companies* is generally fine and encouraged (see
      [`../08-brand-team/`](../08-brand-team/)). Soliciting *investment in the fund* is
      the regulated act. Keep the two distinct.
- [ ] **Substantiate performance claims.** Any return, MOIC, or track-record figure shown
      to prospective LPs must be accurate, sourced, and appropriately caveated. Redstick
      reports on **MOIC** (CLAUDE.md); present it consistently and with dates.
- [ ] **When unsure whether something is "solicitation," ask counsel before posting.**

> **Rule of thumb:** if a communication is designed to get someone to invest in the
> fund, treat it as regulated and route it past counsel. If it's about the market or a
> company, it's brand. Grey areas go to counsel.

---

## 5. Founder-data handling

Redstick receives sensitive, confidential material from founders — decks, cap tables,
financials, data rooms, technical IP. Handling it well is both an ethical obligation and
a competitive asset (founders route deals to funds that don't leak).

- [ ] **Confidentiality by default.** Treat every founder document as confidential
      whether or not an NDA exists. Do not share a company's materials outside the
      diligence team without the founder's consent.
- [ ] **Access control.** Data-room files, triage PDFs, and Notion pipeline entries are
      accessible to the team only. Triage PDFs live in Google Drive; the link is stored
      in Notion (per the deal-triage SKILL) — keep those Drive permissions tight.
- [ ] **Purpose limitation.** Use founder data for evaluating and supporting the
      investment, not for tipping competitors or portfolio companies without consent.
- [ ] **Conflicts overlap.** Passing one company's confidential information to a
      competing company — including a portfolio company — is both a data-handling breach
      and a conflict. See [`03-conflicts-policy.md`](./03-conflicts-policy.md),
      information barriers.
- [ ] **Retention & deletion.** Keep diligence records for passed deals per a defined
      period, then dispose responsibly `[confirm with counsel]` for any legal-hold or
      privacy-law requirements (Canadian PIPEDA / provincial privacy law, US state laws).
- [ ] **AI-tool caution.** When Olli or any AI tool processes founder data, keep it
      within approved, access-controlled systems; do not paste confidential founder
      material into unapproved third-party tools.

---

## 6. Compliance calendar

Right-sized recurring obligations. **All items `[confirm with counsel / admin]` for
exact deadlines, applicability, and forms** — the table shows the *shape* of the year,
not confirmed dates or confirmed obligations.

| Obligation | Typical timing | Owner | Status |
|---|---|---|---|
| **Exempt-offering filings** (US Form D + state notices; Canadian 45-106F1 report of exempt distribution) | Shortly after each closing / first sale | Cam + counsel | `[confirm with counsel]` — trigger & deadline |
| **Annual fund tax returns + LP tax reporting** (US K-1s; Canadian T-slips as applicable) | Annually, post fiscal year-end | Tax advisor | `[confirm]` — due dates & forms |
| **Cross-border withholding filings** | Per distribution / annually | Tax advisor | `[confirm]` — treaty forms |
| **Annual financial statement audit** (if required by LPA/investors) | Annually | Auditor + admin | `[confirm with LPA]` — required? |
| **LP annual/quarterly reporting** (capital accounts, NAV, portfolio) | Per LPA cadence | Cam + admin | Operational — see [`../06-lp-relations-fund-ops/`](../06-lp-relations-fund-ops/) |
| **KYC/AML refresh** for existing LPs | Periodic / on material change | Cam + admin | `[confirm]` — cadence |
| **Ongoing exemption / regulatory filing renewals** | Varies by jurisdiction | Counsel | `[confirm with counsel]` |
| **Compliance & conflicts review** | Semi-annual (firm cadence) + annual conflicts-policy review | Cam | Per [`../../operating-cadence.md`](../../operating-cadence.md) |

> Build the confirmed version of this calendar with counsel and the fund admin once the
> fund's actual exemptions and providers are settled, then track it wherever the team
> tracks the operating cadence.

---

## 7. Compliance checklist (running)

**Before raising**
- [ ] Exemptions relied on (US + each Canadian province) confirmed with counsel
- [ ] Subscription docs + investor questionnaire finalized
- [ ] KYC/AML process and record-keeping defined
- [ ] Marketing/solicitation rules understood by everyone who speaks publicly

**During the raise**
- [ ] Every LP mapped to a jurisdiction and matched to the right exemption
- [ ] KYC + eligibility documented *before* accepting capital
- [ ] No public solicitation of the offering absent a counsel-cleared basis
- [ ] Any performance/track-record claim sourced and caveated

**Ongoing**
- [ ] Post-closing exempt-distribution filings made on time `[confirm]`
- [ ] Annual tax reporting to LPs delivered `[confirm]`
- [ ] Audit completed if required `[confirm with LPA]`
- [ ] Founder-data confidentiality and access controls maintained
- [ ] Semi-annual compliance review done; issues logged and escalated to counsel

---

## The one rule above all

**When in doubt, ask counsel — before acting, not after.** For a two-person emerging
manager, a short call to counsel is cheap. A blown exemption, an unregistered public
solicitation, or a mishandled cross-border withholding is not. Escalate anything novel:
a new investor jurisdiction, a new marketing channel, an SPV, or any structure you
haven't done before.

## Related

- The structure these rules sit on: [`01-fund-structure.md`](./01-fund-structure.md)
- Conflicts & information barriers: [`03-conflicts-policy.md`](./03-conflicts-policy.md)
- LP relations & reporting: [`../06-lp-relations-fund-ops/`](../06-lp-relations-fund-ops/)
- Public communications / brand: [`../08-brand-team/`](../08-brand-team/)
