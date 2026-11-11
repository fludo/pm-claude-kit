---
description: Prepare a meeting agenda with discussion points and likely disagreements
argument-hint: [meeting purpose, attendees, topics]
---

Prepare a **meeting agenda**.
PMI Process Group: **Executing** · Knowledge Area: **Communications**.

Input: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions. If the purpose, attendees, or topics are missing, ask once.

1. **Read first** — the most recent minutes in `docs/meetings/`, if any. Carry forward open
   actions and parked items relevant to this meeting.
2. **Draft** using the structure in `.claude/skills/pmi-project-management/templates/agenda.md`. Mark each item inform / discuss /
   decide. For contentious items, give the likely points of disagreement and a balanced
   framing that keeps the discussion productive.
3. **Close** with "Assumptions / open questions".
4. **Check** — unless *Ready-to-send checks* is `off` in the project context, run the
   ready-to-send checklist at the end of the template against the draft. Fix what the
   material supports — never by inventing content — then report every item as ❌ or ✅
   with a one-line reason, failures first.
5. **Save** — offer `docs/meetings/agenda-YYYY-MM-DD.md` (the meeting date).
