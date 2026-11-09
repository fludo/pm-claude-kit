---
description: Review requirements for ambiguity, testability, and gaps
argument-hint: [paste requirements or point to a file]
---

Review the **requirements** for quality.
PMI Process Group: **Planning** · Knowledge Area: **Scope**.

Requirements: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions. If nothing is pasted, use `docs/requirements.md`; if that does not exist, ask for
the requirements or a file path.

1. **Read first** — `docs/requirements.md` if it exists (keep existing IDs) and the
   objectives and scope in `docs/charter.md`, to check traceability and scope gaps.
2. **Review** each requirement: clear (one interpretation), testable, atomic, feasible and
   consistent, traceable. Rewrite unmeasurable ones into testable form. Do not expand scope
   silently — label anything new "candidate requirement to confirm".
3. **Draft** using the structure in `.claude/skills/pmi-project-management/templates/requirements.md`: register, review findings,
   scope gaps, conflicts/duplicates, open questions for stakeholders.
4. **Save** — offer `docs/requirements.md`.

For a large or contested set, suggest the `requirements-analyst` agent for an independent
second review of the saved file.
