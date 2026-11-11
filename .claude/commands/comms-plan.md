---
description: Draft a communications management plan
argument-hint: [stakeholders / cadence notes, or a brief]
---

Draft or update the **communications management plan**.
PMI Process Group: **Planning** · Knowledge Area: **Communications**.

Input: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions.

1. **Read first** — `docs/stakeholders.md` (every line of the plan ties to a stakeholder
   need; if it does not exist, suggest `/stakeholder-analysis` first) and
   `docs/comms-plan.md` if it exists (update in place).
2. **Draft** using the structure in `${CLAUDE_PLUGIN_ROOT}/.claude/skills/pmi-project-management/templates/comms-plan.md`. Cover at least sponsor/steering,
   client, project team, vendors/suppliers, and the wider organisation. Take the reporting
   cadence from the *Governance* field of the project context; do not invent one.
3. **Check** — unless *Ready-to-send checks* is `off` in the project context, run the
   ready-to-send checklist at the end of the template against the draft. Fix what the
   material supports — never by inventing content — then report every item as ❌ or ✅
   with a one-line reason, failures first.
4. **Save** — offer `docs/comms-plan.md`.
