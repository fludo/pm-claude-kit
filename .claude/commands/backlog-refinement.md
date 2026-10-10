---
description: Refine backlog items — check readiness, acceptance criteria, and sizing
argument-hint: [paste the backlog items / stories to refine]
---

Refine backlog items so they are **ready** to be worked.
Agile ceremony · PMI Process Group: **Planning** · Knowledge Area: **Scope**.

Items: $ARGUMENTS

**Data source:** check the **Jira / Atlassian MCP access** switch in `project-context.md`
(semantics in CLAUDE.md §1). If `allow` and an Atlassian MCP is connected, you may pull the
backlog items live from Jira and note the source + date; otherwise paste-in only.

Use the **requirements-analyst** agent for wording quality. For each item apply a
**definition-of-ready** check:
- **Clear** — one interpretation; no vague terms without a measure.
- **Valuable** — the user/outcome is stated (e.g. "As a … I want … so that …").
- **Testable** — has acceptance criteria you could verify.
- **Small enough** — fits in one iteration; if not, propose a split.
- **Estimable** — enough is known to size it (don't invent the estimate).

Produce a table: item | ready? | issue(s) | proposed revised wording / acceptance criteria.
Then:
- **Items to split** — large items with a suggested breakdown.
- **Open questions for the product owner** — what must be answered before the item is ready.

Do not expand scope silently — label anything new as a candidate to confirm. If nothing is
pasted, ask for the items or a file path.
