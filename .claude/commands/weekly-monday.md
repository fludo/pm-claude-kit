---
description: Monday — draft the weekly status report from this week's data
argument-hint: [paste this week's status data]
---

**Monday routine — weekly status report.**

Status data for this week: $ARGUMENTS

**Data source:** check the **Jira / Atlassian MCP access** switch in `project-context.md`
(semantics in CLAUDE.md §1). If `allow` and an Atlassian MCP is connected, you may pull this
week's data live from Jira and note the source + date; otherwise paste-in only.

If no data is pasted (and no live source is permitted), ask the user to paste this week's
progress, milestones, budget, risks, and issues (or point to `project-status.md`), plus
their house template if they have one.

Then run the **status-report** workflow: produce the report with a RAG status and
executive summary, explain the RAG in one line, and end with "Data I still need". Do not
invent any figure or date. Offer to save to `docs/status/status-YYYY-MM-DD.md`.
