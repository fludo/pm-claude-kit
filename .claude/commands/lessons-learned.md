---
description: Facilitate and document a lessons-learned / retrospective
argument-hint: [phase or project, paste inputs if any]
---

Produce a **lessons-learned report**.
PMI Process Group: **Closing** (also at phase end) · Knowledge Area: **Integration**.
(For a single iteration, use `/retro` instead.)

Input: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions. If inputs are thin, pose facilitation questions to draw out lessons rather than
inventing them.

1. **Read first** — `docs/lessons-learned.md` if it exists (append the new phase; do not
   overwrite earlier ones), plus retros in `docs/sprints/`, `docs/changes/`, and the
   closed and occurred risks in `docs/risk-register.md` as evidence, where present.
2. **Draft** using the structure in `.claude/skills/pmi-project-management/templates/lessons-learned.md`. "What went poorly" names a
   root cause, not a symptom. Every recommendation has an owner or `[owner TBC]`.
3. **Check** — unless *Ready-to-send checks* is `off` in the project context, run the
   ready-to-send checklist at the end of the template against the draft. Fix what the
   material supports — never by inventing content — then report every item as ❌ or ✅
   with a one-line reason, failures first.
4. **Save** — offer `docs/lessons-learned.md`.
