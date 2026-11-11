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
   `${CLAUDE_PLUGIN_ROOT}/.claude/skills/pmi-project-management/templates/stakeholder-register.md`: register, power/interest grid, and engagement actions
   for the highest-priority stakeholders. If stakeholders are not listed, infer a candidate
   set from the project context and label it a draft to confirm.
3. **Flag** assessments of individuals (resistance, influence) as PM judgement — this file
   is sensitive; remind the user to consider who can see it.
4. **Check** — unless *Ready-to-send checks* is `off` in the project context, run the
   ready-to-send checklist at the end of the template against the draft. Fix what the
   material supports — never by inventing content — then report every item as ❌ or ✅
   with a one-line reason, failures first.
5. **Save** — offer `docs/stakeholders.md`.
