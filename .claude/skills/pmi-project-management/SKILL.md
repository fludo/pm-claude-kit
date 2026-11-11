---
name: pmi-project-management
description: Life-cycle frame and shared templates for the PM kit. Use when the task spans several PM artifacts, asks where something fits in the PMI Process Groups or Knowledge Areas, asks which artifact or command to use next, or needs an artifact with no dedicated skill (charter/PID, RACI, requirements, communications plan, meeting agenda/minutes, lessons learned, closure, issue log, decision log). Risk, stakeholder, status, change-control, and agile work have their own skills — prefer those.
allowed-tools: Read(/${CLAUDE_PLUGIN_ROOT}/**)
---

# PMI Project Management

A methodology pack for running projects with Claude as a drafting and reasoning partner.
Claude is **not** a system of record: it never reads live Jira/budgets/Project files and
never invents figures or dates.

## 1. Always establish context first
If this project has no `project-context.md` and no `.claude/CLAUDE.md`, the kit was
installed as a plugin but the project is not set up yet: suggest `/project-init` first.
The project context block from `project-context.md` is loaded with `CLAUDE.md`. Fields
that are blank or still `<...>` are unknown: ask once for what the task needs, then proceed
with clearly labelled assumptions. State the **audience and output format** for every
deliverable.

## 2. Map every task to the life cycle
Name the **Process Group** and **Knowledge Area** each artifact serves.

| Process Group | Typical artifacts |
|---|---|
| Initiating | Charter / PID, initial stakeholder register |
| Planning | Scope & requirements, WBS, schedule, budget, RACI, risk register, comms plan |
| Executing | Meeting agendas/minutes, status updates, stakeholder comms |
| Monitoring & Controlling | Status reports, change requests, risk reviews, issue log, decision log, variance analysis |
| Closing | Lessons learned, closure summary, benefits handover |

**Knowledge Areas:** Integration · Scope · Schedule · Cost · Quality · Resource ·
Communications · Risk · Procurement · Stakeholder.

## 3. Templates — the single source for structure
Each artifact's structure lives in
`${CLAUDE_PLUGIN_ROOT}/.claude/skills/pmi-project-management/templates/`. Read the matching
template and tailor it to the project context; do not restate its structure elsewhere.

Each template ends with a **ready-to-send checklist** in an HTML comment: 4–7 pass/fail
items checkable from the document alone. Commands run it after drafting, and
`/project-check` and the reviewer agents read it from the template, so a per-artifact check
is written there once. A check that compares two files belongs in `/project-check`.
Checklist items never demand a fixed count or forbid `[TBC]`; they ask that every `[TBC]`
is listed under the artifact's open questions.

| Template | Artifact | Command |
|---|---|---|
| `charter.md` | Charter / PID | `/charter` |
| `stakeholder-register.md` | Stakeholder analysis + engagement | `/stakeholder-analysis` |
| `risk-register.md` | Risk register, scoring scale, severity bands | `/risk-register` |
| `raci.md` | Responsibility assignment matrix | `/raci` |
| `requirements.md` | Requirements register + review findings | `/requirements-review` |
| `comms-plan.md` | Communications management plan | `/comms-plan` |
| `agenda.md` | Meeting agenda | `/agenda` |
| `minutes.md` | Meeting minutes | `/minutes` |
| `issue-log.md` | Issue log (things that have already happened) | `/issue-log` |
| `decision-log.md` | Decision log | `/decision-log` |
| `project-status.md` | Current status data the PM maintains (copied to the repo root) | `/import-project` |
| `status-report.md` | Period status report, default RAG definitions | `/status-report`, `/weekly-monday` |
| `change-request.md` | Change request | `/change-request` |
| `sprint-plan.md` | Iteration / sprint plan (agile) | `/sprint-planning` |
| `retro.md` | Iteration retrospective (agile) | `/retro` |
| `lessons-learned.md` | Lessons learned | `/lessons-learned` |
| `closure.md` | Project closure summary | `/closure` |

## 4. Draft inline; use agents for a second pass
Draft artifacts **in the main conversation**, where the pasted data is and where the user
can answer questions. The specialist agents (`risk-manager`, `stakeholder-analyst`,
`status-reporter`, `requirements-analyst`, `meeting-scribe`, `pm-thinking-partner`) start
without the conversation, cannot ask questions, and do not write files. Use them for an
independent review of a **saved** artifact, and pass the file path plus anything else they
need in the brief.

## 5. Discipline (non-negotiable)
- Mark unknown metrics, costs, and dates `[TBC]`; never fabricate.
- Separate **facts** (from supplied data) from **PM judgement** (labelled).
- Flag stakeholder-sensitive and political decisions for the human PM.
- Follow the data governance note in the project context; if it is unfilled, remind the
  user once per session to check policy before handling confidential/client data.
- Read the existing file in `docs/` before writing; update in place and show what changes.
- End artifacts with an "Open questions / data I still need" section.
