---
name: pmi-project-management
description: PMI-aligned project management methodology for running the full project life cycle with Claude. Use whenever the task involves project planning, governance, or PM artifacts — a charter/PID, scope or requirements, schedule, budget, RACI, risk register, stakeholder or communications plan, status report, change request, meeting agenda/minutes, lessons learned, or project closure. Organises work by PMI's five Process Groups and ten Knowledge Areas and enforces draft-for-review discipline.
---

# PMI Project Management

A methodology pack for running projects with Claude as a drafting and reasoning partner.
Claude is **not** a system of record: it never reads live Jira/budgets/Project files and
never invents figures or dates.

## 1. Always establish context first
Before producing an artifact, confirm the **project context block** (role, org/sector,
methodology, governance, constraints, stakeholders, current phase). Read a
`project-context.md` at the repo root if it exists; otherwise ask once, then proceed with
clearly labelled assumptions. State the **audience and output format** for every
deliverable.

## 2. Map every task to the life cycle
Name the **Process Group** and **Knowledge Area** each artifact serves.

| Process Group | Typical artifacts |
|---|---|
| Initiating | Charter / PID, initial stakeholder register |
| Planning | Scope & requirements, WBS, schedule, budget, RACI, risk register, comms plan |
| Executing | Meeting agendas/minutes, status updates, stakeholder comms |
| Monitoring & Controlling | Status reports, change requests, risk reviews, variance analysis |
| Closing | Lessons learned, closure summary, benefits handover |

**Knowledge Areas:** Integration · Scope · Schedule · Cost · Quality · Resource ·
Communications · Risk · Procurement · Stakeholder.

## 3. Templates
Reusable starting points live in `templates/`:
- `charter.md` — project charter / PID
- `risk-register.md` — risk register
- `status-report.md` — period status report
- `raci.md` — responsibility assignment matrix
- `change-request.md` — change request
- `requirements.md` — requirements register + review findings
- `comms-plan.md` — communications management plan
- `stakeholder-register.md` — stakeholder analysis + engagement
- `lessons-learned.md` — lessons learned
- `closure.md` — project closure summary

Load the matching template, then tailor it to the project context.

## 4. Specialist agents
For multi-step reasoning, delegate to the right subagent: `risk-manager`,
`stakeholder-analyst`, `status-reporter`, `requirements-analyst`, `meeting-scribe`, and
`pm-thinking-partner` (to stress-test a recommendation before it goes out).

## 5. Discipline (non-negotiable)
- Mark unknown metrics, costs, and dates `[TBC]`; never fabricate.
- Separate **facts** (from supplied data) from **PM judgement** (labelled).
- Flag stakeholder-sensitive and political decisions for the human PM.
- Remind the user to check data-governance policy before handling confidential/client data.
- End artifacts with an "Open questions / data I still need" section.
