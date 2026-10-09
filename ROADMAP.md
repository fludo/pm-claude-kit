# Roadmap — Future PMI Additions

The current kit covers the core documentation and communication workflow across all five
Process Groups. The items below are intentionally **left out for now** and planned as future
additions. Each notes the PMI Knowledge Area and the proposed form (command / agent / skill).

## Schedule & scope depth
- **WBS builder** — decompose scope into a work breakdown structure.
  *Knowledge Area: Scope · command `/wbs` + template.*
- **Schedule & milestone planner** — activity list, dependencies, critical-path narrative
  (no live Gantt; narrative + table only).
  *Knowledge Area: Schedule · command `/schedule`.*

## Cost & value
- **Cost estimate & budget** — bottom-up / analogous estimate, contingency, baseline.
  *Knowledge Area: Cost · command `/budget` + template.*
- **Earned Value Management (EVM)** — PV/EV/AC, CPI/SPI, EAC/ETC from pasted figures, with
  plain-language interpretation.
  *Knowledge Area: Cost · skill `earned-value` + agent `evm-analyst`.*

## Quality
- **Quality management plan** — quality metrics, acceptance criteria, control approach.
  *Knowledge Area: Quality · command `/quality-plan`.*
- **Quality / deliverable review checklist** — definition of done, review gates.

## Resource
- **Resource / team plan** — roles, RACI integration, capacity, RAG on resourcing.
  *Knowledge Area: Resource · command `/resource-plan`.*

## Procurement
- **Procurement & vendor management** — make-or-buy analysis, SOW outline, contract-type
  guidance, vendor evaluation matrix.
  *Knowledge Area: Procurement · skill `procurement` + command `/procurement`.*

## Agile / hybrid
- **Agile ceremonies pack** — sprint planning, backlog refinement, retrospective, sprint
  review narratives; velocity/burndown interpretation from pasted data.
  *Cross-cutting · skill `agile-delivery`.*
- **Product/sprint backlog grooming** — story quality, INVEST checks (extends
  `requirements-analyst`).

## Governance & reporting
- **Stage-gate / phase-gate review** — readiness checklist and go/no-go recommendation.
  *Knowledge Area: Integration · command `/gate-review`.*
- **Issue log** — distinct from the risk register; open issues tracking.
  *command `/issue-log` + template.*
- **Decision log** — ADR-style record of project decisions.
  *command `/decision-log`.*
- **Benefits realisation plan** — expand the closure template into a standalone artifact.

## Integrations (noted, not built)
- Export helpers to push artifacts into Jira / Monday.com / Asana / MS Project formats
  (CSV / structured output), pending the user's tooling. Claude stays standalone — these
  would format output for copy-in, not call live APIs.

---
*When adding an item: follow the existing pattern — a slash command in `.claude/commands/`,
a specialist in `.claude/agents/`, and/or a methodology skill in `.claude/skills/` with a
template under `pmi-project-management/templates/`. Keep the draft-for-review, no-fabricated-
numbers discipline.*
