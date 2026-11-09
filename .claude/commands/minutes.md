---
description: Turn raw meeting notes or a transcript into minutes with action items
argument-hint: [paste notes or transcript]
---

Turn the notes/transcript into **meeting minutes**.
PMI Process Group: **Executing** · Knowledge Area: **Communications**.

Notes / transcript: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions. If nothing is pasted, ask for the notes or a file path.

1. **Read first** — the matching agenda and the previous minutes in `docs/meetings/`, if
   any, so carried-over actions can be marked done or still open.
2. **Draft** using the structure in `.claude/skills/pmi-project-management/templates/minutes.md`. Be faithful to the source: do not add
   commitments or decisions that were not made, and keep "decided" separate from
   "discussed but not decided". Every action has an owner or is flagged `[owner TBC]`;
   a missing due date is `[TBC]`.
3. **Route** — list decisions to add to `docs/decision-log.md`, issues to add to
   `docs/issue-log.md`, risks raised that are not in `docs/risk-register.md`, and changes
   that need a `/change-request`. Do not update those files without the user's go-ahead.
4. **Close** with "Assumptions / open questions".
5. **Save** — offer `docs/meetings/minutes-YYYY-MM-DD.md` (the meeting date).
