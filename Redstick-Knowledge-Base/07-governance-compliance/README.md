# 07 — Governance & Compliance

How Redstick is structured as a fund, what rules it operates under, and how it keeps
the GP's judgment clean when interests could collide. Governance is not paperwork for
its own sake — it is what lets a two-person emerging manager move fast on deals while
staying defensible to LPs, regulators, and its own future self.

> **⚠️ This section is an operational framework, not legal advice.** Nothing here is a
> substitute for the fund's Limited Partnership Agreement (LPA), the subscription
> documents, or the advice of fund counsel and tax advisors. Every specific legal fact
> — the fund's domicile, entity types, exact management fee and carried interest,
> regulators of record, and filing obligations — must be confirmed against the **actual
> executed LPA and with fund counsel**. Placeholders marked `[confirm with LPA]` or
> `[confirm with counsel]` flag exactly what to fill in. When a placeholder and this
> text disagree with the executed documents, **the executed documents win.**

> Canonical fund facts live in [`../../CLAUDE.md`](../../CLAUDE.md). Where anything here
> disagrees with that file on fund facts (size, check size, thesis), that file wins.

---

## The one-screen version

- **Redstick Ventures Fund I is a $5.0M fund writing $100K / $250K checks.** The
  governance around it should be **right-sized to that** — a small emerging manager,
  not a multi-fund institution. Do not import big-firm bureaucracy the fund does not
  need. See [`01-fund-structure.md`](./01-fund-structure.md).
- **The fund is a private, exempt offering.** It is sold only to qualifying investors
  under offering exemptions, never generally solicited without care, and it keeps
  right-sized KYC/AML and filing discipline. See [`02-regulatory.md`](./02-regulatory.md).
- **The GP's integrity is the fund's core asset.** Conflicts get disclosed and managed
  through a real, written policy with a live register — not handled informally. See
  [`03-conflicts-policy.md`](./03-conflicts-policy.md).
- **When in doubt, ask counsel before acting.** The cost of a call to counsel is always
  smaller than the cost of an exemption blown or a conflict mishandled.

---

## Documents in this section

| # | Doc | What it covers | Nature |
|---|---|---|---|
| 1 | [Fund Structure](./01-fund-structure.md) | GP entity / management company / LP fund vehicle explained generically; fee & carry as concepts `[confirm with LPA]`; US↔Canada cross-border considerations; the roles and who can approve an investment. | Framework + `[confirm]` placeholders |
| 2 | [Regulatory](./02-regulatory.md) | Right-sized compliance: exempt-offering / accredited-investor concepts (US Reg D, Canadian exemptions), KYC/AML on LPs, marketing / general-solicitation caution, founder-data handling, a compliance calendar. | Framework + `[confirm]` placeholders |
| 3 | [Conflicts Policy](./03-conflicts-policy.md) | A real, usable conflicts-of-interest policy: deal allocation, GP angel investing, related-party deals, board conflicts, information barriers, gifts, co-invest fairness, disclosure & recusal, and a conflicts register template. | Concrete policy (adoptable as-is) |

---

## What is framework vs. what is settled policy

Read this distinction before using any document here:

- **Docs 01 and 02 are frameworks with gaps.** They describe how emerging-manager funds
  are *typically* structured and regulated, and they mark every fund-specific legal fact
  as a placeholder. They are a checklist for the conversation with counsel — not answers.
- **Doc 03 is a policy the fund can adopt as written.** A conflicts-of-interest policy
  is about the GP's own conduct, not about entity law, so it can be concrete and
  complete. Counsel should still review it, but it does not depend on fabricated legal
  facts.

---

## How this section connects

```
LPA + subscription docs (executed, held by counsel)
        │  define the real facts behind ↓
Fund Structure (doc 01) ──► Regulatory (doc 02) ──► Conflicts Policy (doc 03)
        │                          │                        │
        ▼                          ▼                        ▼
  Decision authority         Compliance calendar      Conflicts register
  (who approves a deal)      (filings / audit / tax)  (live log, reviewed)
```

- **Upstream:** the [LP Relations & Fund Ops](../06-lp-relations-fund-ops/) section
  covers LP communications, reporting, and fund administration — the operational side
  of the same structure governed here.
- **Sideways:** the [deal-triage skill](../../skills/deal-triage/SKILL.md) and
  [Diligence & Underwriting](../03-diligence-underwriting/) produce the investment
  decisions whose *authority* and *conflicts* are governed by this section.
- **Downstream:** board and observer conduct after investment lives in
  [Portfolio Services](../05-portfolio-services/); the conflicts rules here bind it.

## Owners & cadence

| What | Owner | Cadence |
|---|---|---|
| Fund structure / LPA relationship | Cam + fund counsel | On formation; reviewed annually |
| Regulatory filings + compliance calendar | Cam + fund admin | Per the calendar in doc 02; reviewed semi-annually |
| KYC/AML on new LPs | Cam (+ admin) | At each subscription |
| Conflicts policy + register | Cam (GP) | Register updated on event; policy reviewed annually |
| Counsel check-in | Cam | Before any novel structure, offering, or conflict |

See [`../../operating-cadence.md`](../../operating-cadence.md) for the firm-wide rhythm.
Per that cadence, **compliance is reviewed semi-annually**; the conflicts register is
updated whenever a triggering event occurs, not on a schedule.
