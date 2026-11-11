---
description: Build a RACI responsibility assignment matrix
argument-hint: [list of activities and roles, or a brief]
---

Build or update the **RACI matrix** (Responsible, Accountable, Consulted, Informed).
PMI Process Group: **Planning** · Knowledge Area: **Resource**.

Input: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions.

1. **Read first** — `docs/raci.md` if it exists (update in place), `docs/stakeholders.md`
   for roles, and `docs/charter.md` for deliverables, where present.
2. **Draft** using the structure in `.claude/skills/pmi-project-management/templates/raci.md`. If roles or activities are not given,
   derive a starter set from those files and label it a draft to confirm.
3. **Validate** — complete the template's *Validation* section, listing each row that
   breaks a rule and the proposed fix.
4. **Close** with open questions on roles or activities that need confirmation.
5. **Check** — unless *Ready-to-send checks* is `off` in the project context, run the
   ready-to-send checklist at the end of the template against the draft. Fix what the
   material supports — never by inventing content — then report every item as ❌ or ✅
   with a one-line reason, failures first.
6. **Save** — offer `docs/raci.md`.
