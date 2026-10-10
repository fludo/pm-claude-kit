---
description: Plan an iteration / sprint — goal, capacity, and a proposed backlog selection
argument-hint: [sprint goal, capacity, and candidate backlog items]
---

Plan an **iteration / sprint** (use the team's own term).
Agile ceremony · PMI Process Group: **Planning** · Knowledge Areas: **Scope + Schedule**.

Input: $ARGUMENTS

**Data source:** check the **Jira / Atlassian MCP access** switch in `project-context.md`
(semantics in CLAUDE.md §1). If `allow` and an Atlassian MCP is connected, you may pull the
candidate backlog, estimates, and capacity live from Jira and note the source + date;
otherwise paste-in only.

If capacity, the candidate backlog, or the goal aren't given (and no live source is
permitted), ask once — do not invent velocity, estimates, or capacity. Produce:

1. **Iteration goal** — one sentence the team can rally behind.
2. **Capacity** — available capacity this iteration (from data provided; `[TBC]` if not).
3. **Proposed selection** — table: item | estimate | priority | acceptance criterion |
   fits capacity? Mark the selection as **proposed, not committed** — the team commits.
4. **Definition of done** — the bar each item must meet (carry forward if one exists).
5. **Risks / dependencies** — anything that could block the goal; flag items that should
   go to the risk register.
6. **Not selected** — items considered but left out, with the reason.

End with "Open questions before the team commits". Offer to save to
`docs/sprints/sprint-NN-plan.md`.
