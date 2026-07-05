# Operating Cadence

The OS is only useful if it stays current. This is the review rhythm that keeps it
honest, plus the standing weekly operating loop.

## Weekly operating loop

| Day | Ritual | Owner | Output |
|---|---|---|---|
| Mon | Pipeline review — new inbounds triaged, stage moves, dying deals killed | Cam + Olli | Updated Notion Deal Pipeline |
| Wed | Portfolio check-in — founder reports intake, flags surfaced | Olli | Portfolio Snapshot updated |
| Fri | Weekly close — decisions logged, next-week intros/calls confirmed | Cam | Calendar + inbox zero |
| Ongoing | Inbound triage within 48h of a complete package landing | Olli (via SKILL) | Triage PDF + Notion entry + draft to Cam |

## Maintenance calendar

| Cadence | Action |
|---|---|
| **Monthly** | Refresh fund parameters — deployment %, portfolio count, TVPI, reserves remaining. Update `CLAUDE.md` §1 and section 4. |
| **Quarterly** | Review market landscape, deal-flow metrics, funnel conversion, pipeline health. Update sections 1 and 2. Post-mortem any deal that died mid-pipeline. |
| **Semi-annually** | Refresh competitive positioning (section 8) and the compliance calendar (section 7). |
| **Annually** | Full thesis review, hiring roadmap, and playbook lessons-learned. Post-mortem every investment and rejection at 6 / 12 / 24 months (calibration culture). |

## Change-control rule

The source of record is **this repo**. To change a process:

1. Edit the source file here (branch → PR → merge).
2. Reflect the change in the corresponding Notion page/summary.
3. If the change touches triage logic, update `skills/deal-triage/SKILL.md` and note
   the change in its changelog header so Olli picks it up on the next run.

Never edit Notion first and let the repo drift — that is how two conflicting
"processes" appear. The repo wins.

## Calibration culture

Venture is a high-variance, low-feedback environment. We beat intuition with
discipline and feedback loops:

- Every **rejection** gets a one-line thesis: why we passed, what would have changed our mind.
- Every **investment** gets a memo of record and is revisited at 6 / 12 / 24 months.
- The thesis is updated **quarterly** based on what the data says, not what we wish were true.
