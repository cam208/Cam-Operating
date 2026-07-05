# Automation Layer

The knowledge base and skills define *how Redstick thinks*. This layer defines *what runs
on its own* — the agentic workflows (run by **Olli**) that turn the OS into a system that
operates the business day to day.

> **Status: specification.** These are design docs, not yet wired end-to-end. Each spec
> has a build plan (crawl → walk → run) so we can ship the highest-leverage piece first
> and add autonomy as trust builds. Nothing here bypasses the human-in-the-loop rules below.

## The four workflows

| # | Workflow | Trigger | Core output | Autonomy target |
|---|---|---|---|---|
| 1 | [Inbound Deal Triage](./01-inbound-deal-triage.md) | New deal email / forward to Olli | Triage PDF + Notion pipeline entry + draft to Cam | Semi-auto → auto with review |
| 2 | [Remarkable & PDF Intake](./02-remarkable-pdf-intake.md) | PDF lands in a watched Drive folder | Transcribed, classified, routed to the right workflow | Auto classify, human route |
| 3 | [Portfolio Report Intake](./03-portfolio-report-intake.md) | Founder update email / attachment | Portfolio Snapshot updated + flags surfaced | Auto ingest, human on flags |
| 4 | [Weekly Operating Brief](./04-weekly-operating-brief.md) | Monday 06:00 schedule | One brief: pipeline + portfolio + calendar + asks | Fully auto (read-only) |

They compose: intake (2) feeds triage (1) and portfolio (3); all three feed the weekly
brief (4).

```
        ┌─────────────────────────────┐
Email → │ 2. Remarkable & PDF Intake  │ → classify ─┬─→ 1. Inbound Deal Triage → Notion Pipeline
Drop  → └─────────────────────────────┘             └─→ 3. Portfolio Report Intake → Portfolio Snapshot
                                                                     │
                                    4. Weekly Operating Brief ◄──────┘ (reads pipeline + snapshot + calendar)
```

---

## Shared architecture

### Who runs it
**Olli**, the AI executive assistant (`olli@redstickvc.com`). Every workflow is written as
Olli acting on Cam's behalf. Olli reads the live SKILL and KB files at the start of each
run, so behavior tracks the repo automatically.

### Connectors (data sources)
| Connector | Used for |
|---|---|
| **Gmail** | Inbound deal flow, founder updates, LP comms (read + draft) |
| **Google Drive** | Deck/data-room storage, Remarkable PDF exports, triage-PDF archive |
| **Notion** | Deal Pipeline DB (`77829e04-0a0c-4ee6-94d5-1807b9ea0241`), Portfolio Snapshot, KB |
| **Google Calendar** | Scheduling intro calls, reading the week for the brief |
| **Otter.ai** | Founder/reference call transcripts |
| **Limitless** | Ambient meeting/conversation capture for context |

### Human-in-the-loop policy (non-negotiable)
| Action | Autonomy |
|---|---|
| Read, transcribe, classify, extract, summarize | ✅ Autonomous |
| Write to Notion pipeline / snapshot (internal record) | ✅ Autonomous, logged |
| **Draft** an email to a founder / LP / third party | ✅ Autonomous — saved as a draft |
| **Send** any external email | ⛔ Cam approves and sends |
| **Investment decision** (ADVANCE / PASS / follow-on) | ⛔ Cam decides; Olli only recommends |
| Move money, sign, or commit the fund | ⛔ Never automated |

Default posture: **Olli prepares, Cam commits.** Anything outward-facing or irreversible
stops at a draft.

### Guardrails (inherited from `../CLAUDE.md`)
- **Provenance always.** Every extracted figure cites its source (document + page). Mark
  inferences `[Assumed]`, conversation-sourced data `[to confirm on call]`.
- **Never present an inference as fact.** No fabricated numbers, ever.
- **Fund facts are hard-coded.** $100K/$250K checks, MOIC, $5M fund-returner bar. If input
  implies a different fund size/check, **flag the conflict, don't silently use it.**
- **Currency labels.** Every dollar figure is `USD` or `CAD`.
- **Privacy.** Founder data stays in Redstick systems; nothing is sent to third parties
  without Cam's go. See `../Redstick-Knowledge-Base/07-governance-compliance/`.

### Spec template
Each workflow spec follows the same shape: Purpose → Trigger → Inputs → Pipeline →
Outputs → Human-in-the-loop → Guardrails → Failure modes → Build plan (crawl/walk/run) →
Open questions.

### How these get built
The workflows are implemented as **scheduled or event-driven Claude/Olli runs** (e.g. the
`claude-code-remote` trigger/cron facilities, or a watched-folder poll). This layer specs
*behavior and contracts*; the runtime wiring is a build task per the roadmap in each doc.
