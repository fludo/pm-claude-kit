---
description: Map and classify stakeholders on a power/interest grid with engagement plan
argument-hint: [list of stakeholders or a brief]
---

Produce or update the **stakeholder analysis**.
PMI Process Group: **Initiating / Planning** · Knowledge Area: **Stakeholder**.

Input: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions.

1. **Read first** — `docs/stakeholders.md` if it exists (update in place) and
   `docs/charter.md` for the sponsor and governance names, where present.
2. **Draft** following the `stakeholder-management` skill and the structure in
   `.claude/skills/pmi-project-management/templates/stakeholder-register.md`: register, power/interest grid, and engagement actions
   for the highest-priority stakeholders. If stakeholders are not listed, infer a candidate
   set from the project context and label it a draft to confirm.
3. **Flag** assessments of individuals (resistance, influence) as PM judgement — this file
   is sensitive; remind the user to consider who can see it.
4. **Save** — offer `docs/stakeholders.md`.
