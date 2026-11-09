---
description: Record a project decision, or review the decision log
argument-hint: [the decision and who made it, or leave blank to review]
---

Add to or review the **decision log**.
PMI Process Group: **Monitoring & Controlling** · Knowledge Area: **Integration**.

Input: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions.

1. **Read first** — `docs/decision-log.md` if it exists (new decisions take the next free
   `D` number) and, if the input points to a meeting, the matching minutes in
   `docs/meetings/`.
2. **Check it is a decision** — something actually decided, by a named person or body with
   the authority to decide it. If the input shows it was only discussed, or does not say
   who decided, do not log it as decided: list it under "Decisions pending" and ask.
3. **Draft** using the structure in `.claude/skills/pmi-project-management/templates/decision-log.md`. Record the reason and the
   options considered only as far as the input states them; `[TBC]` otherwise. Never tidy
   a decision into something firmer than what was said.
4. **Supersede, do not edit** — if the new decision changes an earlier one, add a new row
   and set the old row to "Superseded by Dn".
5. **With no input, review** — list decisions pending past their needed-by date, and
   decisions in this period's minutes that are not in the log.
6. **Route** — flag a decision that changes scope, schedule, or cost as needing a
   `/change-request`, and one that creates or removes a risk for the risk register.
7. **Close** with "Assumptions / open questions".
8. **Save** — offer `docs/decision-log.md`, summarising the rows added or superseded first.
