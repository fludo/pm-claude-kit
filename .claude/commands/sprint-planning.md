---
description: Plan an iteration / sprint — goal, capacity, and a proposed backlog selection
argument-hint: [sprint goal, capacity, and candidate backlog items]
---

Plan an **iteration / sprint** (use the team's own term).
Agile ceremony · PMI Process Group: **Planning** · Knowledge Areas: **Scope + Schedule**.

Input: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions. If capacity, the candidate backlog, or the goal are not given, ask once — do not
invent velocity, estimates, or capacity.

1. **Read first** — list `docs/sprints/` and take the next free `sprint-NN`. Read the
   previous plan (carry forward the definition of done and unfinished items) and the
   previous retro (open actions), where present.
2. **Draft** using the structure in `.claude/skills/pmi-project-management/templates/sprint-plan.md`. The selection is **proposed, not
   committed** — the team commits. Give a reason for each item not selected. Flag risks
   and dependencies that belong in the risk register.
3. **Close** with "Open questions before the team commits".
4. **Save** — offer `docs/sprints/sprint-NN-plan.md`.
