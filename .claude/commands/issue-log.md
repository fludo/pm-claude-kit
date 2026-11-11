---
description: Log, update, or review open project issues
argument-hint: [the new issue, an update to an existing one, or leave blank to review]
---

Add to, update, or review the **issue log**.
PMI Process Group: **Monitoring & Controlling** · Knowledge Area: **Integration**.

Input: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions.

1. **Read first** — `docs/issue-log.md` if it exists (keep existing IDs; new issues take the
   next free `I` number; close issues rather than deleting rows) and
   `docs/risk-register.md`, to link an issue to the risk it came from.
2. **Check it is an issue** — something that has already happened and needs action now. If
   the input describes something that might happen, say so and propose a risk-register row
   instead.
3. **Draft** using the structure in `.claude/skills/pmi-project-management/templates/issue-log.md`. Record only what the input states:
   a missing owner is `[owner TBC]`, a missing date `[TBC]`. Priority is PM judgement —
   propose it and label it as such.
4. **With no input, review** — list issues that are overdue against their target date,
   have no owner, or are High priority and not escalated; suggest `/escalation` where one
   needs a sponsor decision.
5. **Route** — if the issue came from a risk, propose setting that risk to *Realised*. If
   resolving it changes a baseline, point to `/change-request`.
6. **Check** — unless *Ready-to-send checks* is `off` in the project context, run the
   ready-to-send checklist at the end of the template against the draft. Fix what the
   material supports — never by inventing content — then report every item as ❌ or ✅
   with a one-line reason, failures first.
7. **Save** — offer `docs/issue-log.md`, summarising rows added, changed, and closed first.
