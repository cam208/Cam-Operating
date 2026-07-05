# CLAUDE.md — Redstick Ventures Operating System

This repository is the **institutional operating system for Redstick Ventures**. Any
Claude session working in this repo operates as an extension of the Redstick team.
Read this file first. It is the canonical source of truth for fund facts, thesis,
and process. Where a document elsewhere disagrees with this file, **this file wins**
and the other document should be corrected.

> This is the file-backed twin of the Notion Knowledge Base. Notion is for
> navigation and live databases (the Deal Pipeline); this repo is the versioned
> source of record for process, frameworks, and templates.

---

## 1. What Redstick is

Redstick Ventures is an early-stage venture capital firm investing in **AI and
robotics that make food systems more productive** — across the entire value chain,
from farm to consumer.

| Fact | Value |
|---|---|
| **Thesis** | AI & robotics for food productivity, farm → consumer |
| **Stage** | Pre-seed to Series A (concentration at pre-seed/seed) |
| **Geography** | North America (US + Canada) |
| **Fund** | Redstick Ventures Fund I |
| **Fund I size** | **$5.0M** (live modeling figure, confirmed Apr 20 2026; ~$4.725M net) |
| **Check size** | **$100K or $250K only** — never $500K, never $1M (that is future-fund territory) |
| **Deployment** | ~1/3 of Fund I deployed as of mid-2026 |
| **Target portfolio** | 15–20 companies (power-law construction) |
| **Return unit** | **MOIC** (Fund I is evaluated on the multiple, not IRR) |
| **Fund-returner bar** | A single deal must return **$5M** to the fund |

### The team
- **Cam Crowder** — General Partner. Former Tim Hortons franchisee and multi-unit
  restaurant operator; brings operator-side food-industry judgment.
  `cam@redstickvc.com` · 519-919-2703
- **Shane Larisey** — Co-founder. Manufacturing and supply-chain engineering
  background; brings production and supply-chain diligence.
- **Olli** — AI Executive Assistant. Runs deal triage, inbox/calendar coordination,
  and portfolio-report intake. Operates from `olli@redstickvc.com`. Olli reads the
  live SKILL files in `skills/` at the start of each task.

---

## 2. The thesis in four vectors

Every deal is tagged to exactly one technology vector (or `Off-Thesis`).

| Vector | Definition |
|---|---|
| **Labour Productivity (Robotics)** | Physical systems replacing manual labor in food production, processing, and service |
| **Optimization (CV/Sensing)** | AI vision / sensing for grading, sorting, QC, yield |
| **Decision Automation (AI/Ops)** | AI automating forecasting, inventory, scheduling, compliance |
| **Input Efficiency (Bio/Materials)** | Novel materials / bioprocesses improving production efficiency |

---

## 3. How we underwrite (the short version)

Full detail: `Redstick-Knowledge-Base/03-diligence-underwriting/`. The one-screen version:

**7-stage pipeline with hard gates** — process discipline beats single-point intuition:

1. Deck Screen (15–30 min) — *Thesis fit?*
2. Founder Call (45–90 min) — *Founder signal?*
3. Data Room (4–8 hr) — *Diligence feasible?*
4. References (3–5 calls) — *Integrity + track record?*
5. Technical DD (6–12 hr) — *Technical risk acceptable?*
6. IC Memo (8–12 hr) — *Risk-adjusted return ≥ 5×?*
7. Terms & Close — *Terms acceptable?*

**Five-lens scorecard (live weighting, Apr 2026):**
`(Founder×0.40) + (Market×0.25) + (Tech×0.15) + (UnitEcon×0.15) + (DealTerms×0.05)` → X.X / 5.0

> Note: the original weighting (Founder 50 / Market 20 / UnitEcon 10) was superseded
> on 2026-04-20. Use the 40/25/15/15/5 weighting. No lens below 2.0 may earn an ADVANCE.

**Non-negotiable Fund I rules for any modeling or triage:**
- Model **$100K and $250K side by side.** Never use the founder's ask. Never $500K/$1M.
- **No target ownership.** Fund I is check-size-driven. Never pass a deal for "ownership too low" or "round too small."
- **Report EV as MOIC @ cap** (check-size-agnostic, comparable across the pipeline).
- **Bear-case floor: ≥ 20% fail probability** at pre-seed/seed regardless of traction.
- Every financial figure **cites its source** (document + page/section).

---

## 4. Repository map

```
README.md                    ← start here (human-facing overview)
CLAUDE.md                    ← this file (canonical facts + operating rules)
operating-cadence.md         ← maintenance rhythms (monthly/quarterly/annual)
skills/
  deal-triage/SKILL.md       ← live triage skill (drives Olli); git-versioned
automation/                  ← agentic workflow specs (the "operates my business" layer)
  01-inbound-deal-triage.md  ← auto-triage loop
  02-remarkable-pdf-intake.md← Remarkable/PDF intake + routing
  03-portfolio-report-intake.md ← founder updates → Portfolio Snapshot + flags
  04-weekly-operating-brief.md  ← Monday brief (pipeline + portfolio + calendar)
Redstick-Knowledge-Base/
  README.md                  ← the KB hub (mirrors the Notion index)
  01-fund-strategy-thesis/   ← thesis, fund parameters, market landscape
  02-deal-sourcing-pipeline/ ← channels, CRM ops, funnel math, network
  03-diligence-underwriting/ ← philosophy, founder assessment, EV modeling, terms, sector DD
  04-portfolio-construction/ ← check sizing, concentration, SPV/follow-on
  05-portfolio-services/     ← onboarding, founder support, board governance
  06-lp-relations-fund-ops/  ← LP comms, reporting, fund admin
  07-governance-compliance/  ← fund structure, regulatory, conflicts
  08-brand-team/             ← positioning, thought leadership, hiring
  09-playbooks/              ← first 90 days, markups, crisis, exits
```

---

## 5. Live systems this repo connects to

- **Notion — Deal Pipeline (Fund I)**: data source ID `77829e04-0a0c-4ee6-94d5-1807b9ea0241`.
  Every triage logs here. Search before creating; update if the company exists, never duplicate.
- **Notion — Knowledge Base hub**: the navigation/summary twin of this repo.
- **Google Drive**: triage PDFs and data-room files. Olli uploads triage PDFs and pastes the link into the Notion `Triage Doc` field.
- **Gmail / Calendar**: inbound deal flow, LP comms, scheduling (Olli coordinates).

---

## 6. Working rules for Claude in this repo

- Treat Section 1 facts as hard-coded. If a task implies a different fund size or
  check size, stop and flag the conflict rather than silently using another number.
- When updating process, edit the **source file in this repo**, then reflect the
  change in Notion — not the other way around.
- Keep every dollar figure labeled `USD` or `CAD`. Fund reporting currency is USD;
  many deals are CAD.
- Never present an inference as a fact. Mark inferences `[Assumed]` and
  conversation-sourced data `[to confirm on call]`.
- Strategic-LP-fit flags matter for reporting (FCC / CFIN / policy capital):
  Canadian founders, female founders, Indigenous founders, clean-tech angle,
  regional economic development.
