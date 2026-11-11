---
description: Draft a change request for integrated change control
argument-hint: [the proposed change]
allowed-tools: Read(/${CLAUDE_PLUGIN_ROOT}/**)
---

Draft a **change request (CR)** for integrated change control.
PMI Process Group: **Monitoring & Controlling** · Knowledge Area: **Integration**.

Proposed change: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions.

1. **Read first** — list `docs/changes/` and take the next free `CR-NNN`. Read
   `docs/charter.md` (the scope and baseline the change is measured against) and
   `docs/risk-register.md`, if present.
2. **Draft** following the `change-control` skill and the structure in
   `${CLAUDE_PLUGIN_ROOT}/.claude/skills/pmi-project-management/templates/change-request.md`. Assess impact on scope, schedule, cost, quality, risk, and
   resources; unknowns are `[TBC]`, never invented. Options always include
   "reject / do nothing", with a recommendation. Leave the decision block for the CCB.
3. **Close** with "Information needed to assess impact" and note any risk-register or
   schedule updates that approval would trigger.
4. **Check** — unless *Ready-to-send checks* is `off` in the project context, run the
   ready-to-send checklist at the end of the template against the draft. Fix what the
   material supports — never by inventing content — then report every item as ❌ or ✅
   with a one-line reason, failures first, in the language the user writes in (not the
   Artifact language).
5. **Save** — offer `docs/changes/CR-NNN.md`.
