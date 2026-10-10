---
description: Draft a period status report from pasted project data
argument-hint: [paste status data, or point to a file]
---

Draft a **status report** from the data provided.
PMI Process Group: **Monitoring & Controlling** · Knowledge Area: **Communications**.

Project data: $ARGUMENTS

**Data source:** check the **Jira / Atlassian MCP access** switch in `project-context.md`
(semantics in CLAUDE.md §1). If `allow` and an Atlassian MCP is connected, you may pull the
status live from Jira and note the source + date; otherwise paste-in only.

If no data is pasted (and no live source is permitted), ask the user to paste progress,
milestones, budget, risks, and issues — or point to `project-status.md`. Do not invent any
metric, date, or progress.

Follow the **status-reporter** structure: header + RAG, executive summary, progress,
milestones table, budget/schedule (if provided), top risks & issues, decisions/escalations
needed, look ahead. Explain the RAG rationale in one line and end with "Data I still need".

If the user has a house template, follow it exactly. Offer to save to
`docs/status/status-YYYY-MM-DD.md`.
