---
name: status-reporting
description: Turn project-status.md or pasted project data into a clear period/weekly status report with a RAG status and executive summary. Use when the task mentions status report, weekly report, progress update, project dashboard narrative, RAG/traffic-light status, or steering-committee update. PMI Knowledge Area: Communications.
---

# Status Reporting

Convert the data the user pastes (or `project-status.md`) into an audience-ready report.
**Never invent** progress, metrics, or dates — organise what you're given and mark gaps
`[TBC]`.

**Inputs:** `project-status.md` at the repo root plus any data pasted in the conversation;
where they differ, the pasted data wins. A file still holding only template placeholders
counts as missing. With neither, ask. Also read the newest report in `docs/status/` dated
before this one and `docs/risk-register.md` for continuity.

**RAG:** derive it from the *Status tolerances* in the project context and give a one-line
rationale that names the tolerance. If the field says "kit defaults", apply the thresholds
in the template. If it is unfilled, apply them and write "PM judgement — tolerances [TBC]".
Do not let the RAG drift from the previous report without saying what changed.

**Continuity:** state the trend against the last report, every milestone forecast that
moved, and carried-over actions. If the new data contradicts the last report, say so.

**Writing:** an executive summary a sponsor can read in 20 seconds — where we are, whether
we are on track, the one thing needing attention. Tables for anything with dates or
numbers. Always show budget and schedule: if a measure has no data, mark it `[TBC]`, list
it under "Data I still need", and report no better than Amber. Separate facts from PM
judgement. End with "Data I still need".

Use the template at `${CLAUDE_PLUGIN_ROOT}/.claude/skills/pmi-project-management/templates/status-report.md`, or
the user's house template if they supply one (map their data into it exactly). Draft
inline; for a pre-send check of a saved report, use the `status-reporter` agent.
