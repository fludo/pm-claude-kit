---
name: change-control
description: Document and assess project changes through integrated change control. Use when the task mentions a change request, scope change, variation, change control board (CCB), baseline change, or assessing the impact of a proposed change on scope/schedule/cost/quality. PMI Knowledge Area: Integration.
---

# Change Control

Run proposed changes through integrated change control so impacts are understood before a
baseline moves.

For each change produce: description · reason/driver · **impact assessment** across scope,
schedule, cost, quality, risk, and resources · options considered (always include
"reject / do nothing") with a recommendation · affected stakeholders & approvals · the CCB
decision block.

Use the template at `.claude/skills/pmi-project-management/templates/change-request.md`.
Measure impact against the baseline in `docs/charter.md`. Number the CR by listing
`docs/changes/` and taking the next free `CR-NNN`. State unknown impacts as `[TBC]` and
never invent figures. End with "Information needed to assess impact". The decision belongs
to the CCB — leave the decision block blank. Flag any change that, if approved, should
update the risk register, schedule, or charter.
