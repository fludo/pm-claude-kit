# Claude Project Manager

A PMI-aligned `.claude` boilerplate that turns Claude Code into a project management
assistant. It follows PMI's five Process Groups and ten Knowledge Areas, with a practical
working style: rich context, stated output format and audience, reasoning over lookup,
paste-the-data-in, and human judgement on the political calls.

## Quick start
1. Fill in **`project-context.md`** at the repo root (Claude reads it automatically).
2. Use a slash command, e.g. `/charter`, `/risk-register`, `/status-report`.
3. For multi-step work, Claude delegates to the matching specialist agent.

## What's inside

```
.claude/
├── CLAUDE.md                 # Project context block + working principles (auto-loaded)
├── settings.json             # Permissions
├── agents/                   # Specialist subagents
│   ├── risk-manager.md
│   ├── stakeholder-analyst.md
│   ├── status-reporter.md
│   ├── requirements-analyst.md
│   ├── meeting-scribe.md
│   └── pm-thinking-partner.md
├── commands/                 # Slash commands (one-shot artifacts)
│   ├── charter.md            /charter          → Charter / PID
│   ├── risk-register.md      /risk-register    → Risk register
│   ├── status-report.md      /status-report    → Status report
│   ├── raci.md               /raci             → RACI matrix
│   ├── comms-plan.md         /comms-plan       → Communications plan
│   ├── agenda.md             /agenda           → Meeting agenda
│   ├── minutes.md            /minutes          → Meeting minutes
│   ├── change-request.md     /change-request   → Change request
│   ├── lessons-learned.md    /lessons-learned  → Lessons learned
│   ├── closure.md            /closure          → Closure summary
│   ├── escalation.md         /escalation       → Escalation email
│   ├── stakeholder-analysis.md /stakeholder-analysis → Stakeholder map
│   ├── requirements-review.md  /requirements-review  → Requirements QA
│   ├── weekly-monday.md      /weekly-monday    → Weekly status (Monday routine)
│   ├── weekly-friday.md      /weekly-friday    → End-of-week loose-ends scan
│   ├── import-project.md     /import-project   → Onboard an in-flight project
│   └── project-check.md      /project-check    → Audit setup / import readiness
└── skills/                   # Methodology packs (auto-trigger on matching tasks)
    ├── pmi-project-management/  # Master skill + templates/ (8 reusable templates)
    ├── risk-management/
    ├── stakeholder-management/
    ├── status-reporting/
    └── change-control/
```

## Mapping to PMI

| Process Group | Commands |
|---|---|
| Initiating | `/charter`, `/stakeholder-analysis` |
| Planning | `/risk-register`, `/raci`, `/comms-plan`, `/requirements-review` |
| Executing | `/agenda`, `/minutes`, `/escalation` |
| Monitoring & Controlling | `/status-report`, `/change-request`, `/weekly-monday`, `/weekly-friday` |
| Closing | `/lessons-learned`, `/closure` |
| Setup / any phase | `/import-project` (onboard an in-flight project), `/project-check` (audit it's correctly set up) |

## Importing an in-flight project
Fastest path — run **`/import-project`**: it interviews you for the context block, ingests
whatever you paste (Jira/MS Project exports, old status emails, a charter draft, notes),
sorts it into the right `docs/` files, stubs the rest from templates, and finishes with a
readiness report.

Prefer to do it by hand? The manual equivalent:
1. Fill `project-context.md` and set **Current phase** to where the project actually is.
2. Copy any existing artifacts (charter, risk register, latest status, stakeholder list,
   decisions) into the matching files under `docs/` — commands then update them in place.
3. Paste data that lives in other tools (Jira, MS Project, spreadsheets, email) when
   running a command; Claude organises it and never invents figures.
4. Run **`/project-check`** to see what's present, missing, stale, or inconsistent, then
   let the suggested commands backfill the gaps.

## Ground rules Claude follows
- Never reads live Jira/budgets/Project — **paste the data in**.
- Never fabricates numbers or dates — unknowns are marked `[TBC]`.
- Separates facts from PM judgement, and flags political/stakeholder calls for you.
- Every artifact is a **draft for human review** before it reaches a sponsor or client.
- Reminds you to check data-governance policy before handling confidential data.

Generated artifacts are suggested into `docs/` (e.g. `docs/charter.md`,
`docs/risk-register.md`, `docs/status/`, `docs/meetings/`, `docs/changes/`).

## Roadmap
Planned PMI additions (WBS, schedule, cost/EVM, quality, resource, procurement, agile,
gate reviews, issue/decision logs) are tracked in [`ROADMAP.md`](ROADMAP.md).
