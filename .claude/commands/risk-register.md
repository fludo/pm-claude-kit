---
description: Build or update a risk register with analysis and responses
argument-hint: [context, sector, or paste existing risks]
allowed-tools: Read(/${CLAUDE_PLUGIN_ROOT}/**)
---

Build or update the **risk register**.
PMI Process Group: **Planning / Monitoring & Controlling** · Knowledge Area: **Risk**.

Input: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions.

1. **Read first** — `docs/risk-register.md` if it exists. Update it in place: keep existing
   IDs, change status rather than deleting rows, and give new risks the next free ID. Also
   read `docs/charter.md` (scope, constraints, high-level risks) if present.
2. **Analyse** following the `risk-management` skill, using the structure and scoring scale
   in `${CLAUDE_PLUGIN_ROOT}/.claude/skills/pmi-project-management/templates/risk-register.md` (or the *Risk scoring* scale in the project context).
3. **Add** after the table: candidate risks to confirm for this sector/technology, the top
   5 by severity, and open questions for the PM where owners or data are missing.
4. **Check** — unless *Ready-to-send checks* is `off` in the project context, run the
   ready-to-send checklist at the end of the template against the draft. Fix what the
   material supports — never by inventing content — then report every item as ❌ or ✅
   with a one-line reason, failures first.
5. **Save** — offer `docs/risk-register.md`. If the file already exists, summarise the rows
   added, changed, and closed before writing.

If a risk has already occurred, set its status to *Realised* and propose a row for
`docs/issue-log.md` (see `/issue-log`) rather than leaving it open as a risk.

For a fresh-eyes challenge of a saved register, suggest the `risk-manager` agent.
