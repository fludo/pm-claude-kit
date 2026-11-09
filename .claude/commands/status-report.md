---
description: Draft a period status report from project-status.md or pasted data
argument-hint: [paste status data, or leave blank to use project-status.md]
---

Draft a **status report**.
PMI Process Group: **Monitoring & Controlling** · Knowledge Area: **Communications**.

Project data: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions.

1. **Get the data** — use what is pasted above. If nothing is pasted, read
   `project-status.md` at the repo root. If neither exists, ask the user to paste progress,
   milestones, budget, risks, and issues, and stop until they do. Never invent a metric,
   date, or progress.
2. **Read for continuity** — the newest report in `docs/status/` (by the date in its
   filename), `docs/risk-register.md`, and `docs/issue-log.md`, if present. Use them for
   the trend, milestone forecast movements, carried-over actions, and top risks and issues.
   Build "Decisions / escalations needed" from the project data in step 1 plus the pending
   section of `docs/decision-log.md`, listing an item once if it appears in both. If the
   new data contradicts the previous report, say so rather than smoothing it over.
3. **Draft** following the `status-reporting` skill and the structure in
   `.claude/skills/pmi-project-management/templates/status-report.md`. If the user has a house template, follow it exactly instead.
4. **RAG** — derive it from the *Status tolerances* in the project context and give a
   one-line rationale. If the field says "kit defaults", apply the template thresholds and
   name the one that set the colour. If it is unfilled, apply the same thresholds and write
   "PM judgement — tolerances [TBC]".
5. **Close** with "Data I still need".
6. **Save** — offer `docs/status/status-YYYY-MM-DD.md` (the report date).
