---
description: Draft a project closure summary / closeout report
argument-hint: [project, paste final status if any]
---

Draft a **project closure summary (closeout report)**.
PMI Process Group: **Closing** · Knowledge Area: **Integration**.

Input: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions.

1. **Read first** — `docs/charter.md` (objectives and baseline), the newest report in
   `docs/status/`, `docs/risk-register.md` and `docs/issue-log.md` (open items to hand over),
   `docs/decision-log.md`, `docs/changes/`
   (approved changes to the baseline), and `docs/lessons-learned.md`, where present.
2. **Draft** using the structure in `.claude/skills/pmi-project-management/templates/closure.md`. Performance against baseline comes
   from data only. Mark unverified results `[TBC]`; do not claim an objective was met
   without evidence. Link to the lessons-learned report rather than repeating it.
3. **Save** — offer `docs/closure.md`.
