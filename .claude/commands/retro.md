---
description: Facilitate a fast iteration retrospective with action items
argument-hint: [paste the iteration's notes / observations, or leave blank to facilitate]
---

Run an **iteration retrospective** (retro) — fast and action-oriented.
Agile ceremony · PMI Process Group: **Monitoring & Controlling** · Knowledge Area: **Integration**.
(For a project/phase-level review by knowledge area, use `/lessons-learned` instead.)

Input: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions. If no notes are pasted, pose a few facilitation prompts to draw out observations
rather than inventing them.

1. **Read first** — list `docs/sprints/` to find the iteration number and read the previous
   retro, if any. Its open actions go in "Carry-over".
2. **Draft** using the structure in `.claude/skills/pmi-project-management/templates/retro.md`. "What didn't" names a root cause, not a
   symptom. Every action has an owner or `[owner TBC]`. Keep actions to the few that will
   actually get done. Be faithful to the notes; do not invent what the team said.
3. **Check** — unless *Ready-to-send checks* is `off` in the project context, run the
   ready-to-send checklist at the end of the template against the draft. Fix what the
   material supports — never by inventing content — then report every item as ❌ or ✅
   with a one-line reason, failures first.
4. **Save** — offer `docs/sprints/sprint-NN-retro.md`.
