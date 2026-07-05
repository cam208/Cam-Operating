# Skills

Live, git-versioned instruction files that Claude / Olli read at the start of a task.
Keeping them in the repo (rather than only in Notion) gives us version history,
review-before-merge, and a single source of truth.

| Skill | Purpose | Run by |
|---|---|---|
| [`deal-triage/SKILL.md`](./deal-triage/SKILL.md) | Full inbound-deal triage: read all docs → score → market stress test → PDF → Notion log → draft to Cam | Olli, on every complete inbound package |

## How these stay in sync with Notion

The Notion "SKILL — …(Live Instructions)" pages and these files describe the same
process. **This repo is the source of record.** When the process changes, edit the
file here, bump the changelog header, then mirror the summary into Notion. See
[`../operating-cadence.md`](../operating-cadence.md) → Change-control rule.
