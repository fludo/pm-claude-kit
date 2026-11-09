---
description: Monday — draft the weekly status report from this week's data
argument-hint: [paste this week's status data, or leave blank to use project-status.md]
---

**Monday routine — weekly status report.**

Status data for this week: $ARGUMENTS

Follow the steps in `.claude/commands/status-report.md`, with these weekly settings:

- **Period** — the week just ended (Monday–Sunday) unless the user says otherwise.
- **Stale data check** — if using `project-status.md` and its "As of" date is more than a
  week old, say so and ask whether to proceed or wait for an update.
- **Week-over-week** — the "Changes since last report" section is mandatory: compare with
  last week's report in `docs/status/` and list what moved.
- **Loose ends** — if the week's minutes in `docs/meetings/` (or the latest minutes, if
  none are from that week) left actions without owners, list them under "Decisions /
  escalations needed".
