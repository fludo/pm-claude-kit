---
description: Prepare for increment / PI / quarter planning — objectives, dependencies, risks
argument-hint: [the increment's candidate objectives, teams, and known constraints]
---

Prepare for **increment / PI / quarter planning** (use the team's own term) — this is
*preparation*, not the event itself.
Agile ceremony · PMI Process Group: **Planning** · Knowledge Areas: **Scope + Schedule + Risk**.

Input: $ARGUMENTS

**Data source:** check the **Jira / Atlassian MCP access** switch in `project-context.md`
(semantics in CLAUDE.md §1). If `allow` and an Atlassian MCP is connected, you may pull the
candidate epics/features, dependencies, and capacity live from Jira and note the source +
date; otherwise paste-in only.

Methodology-agnostic: works whether or not the team runs SAFe. Do not invent capacity,
velocity, or dates. Produce:

1. **Increment objective(s)** — the outcomes this increment commits to, each with a
   measure of success.
2. **Candidate scope** — the features/epics in play, ranked, with their value and rough
   size (`[TBC]` where unknown).
3. **Dependencies** — table: dependency | needed from | needed by | status. Highlight
   cross-team ones, which are the usual failure point.
4. **Risks & assumptions** — what could derail the increment; route material ones to the
   risk register.
5. **Capacity vs. demand** — a reality check, only from data provided.
6. **Open questions to resolve before the planning event** — decisions and data still needed.

Flag anything cross-team or political as a judgement call for the PM. Offer to save to
`docs/sprints/increment-NN-prep.md`.
