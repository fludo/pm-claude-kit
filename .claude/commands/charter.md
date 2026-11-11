---
description: Draft a project charter / Project Initiation Document (PID)
argument-hint: [project name or brief]
allowed-tools: Read(/${CLAUDE_PLUGIN_ROOT}/**)
---

Draft or update the **project charter / Project Initiation Document (PID)**.
PMI Process Group: **Initiating** · Knowledge Area: **Integration**.

Input / brief: $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent, which cannot see what
was pasted here or ask the user questions. For anything unknown in the project context, ask once, then proceed with labelled
assumptions.

1. **Read first** — `docs/charter.md` if it exists (update it and bump the version rather
   than starting over) and `docs/stakeholders.md` for sponsor and governance names.
2. **Draft** using the structure in `${CLAUDE_PLUGIN_ROOT}/.claude/skills/pmi-project-management/templates/charter.md`. Objectives are SMART, each with a
   success measure. Scope lists explicit exclusions. Limit high-level risks to the top 5.
   Budget and dates come only from supplied data; otherwise `[TBC]`.
3. **Close** with "Open questions before approval".
4. **Check** — unless *Ready-to-send checks* is `off` in the project context, run the
   ready-to-send checklist at the end of the template against the draft. Fix what the
   material supports — never by inventing content — then report every item as ❌ or ✅
   with a one-line reason, failures first, in the language the user writes in (not the
   Artifact language).
5. **Save** — offer `docs/charter.md`.
