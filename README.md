# PM Kit for Claude Code

A PMI-aligned `.claude` boilerplate that turns Claude Code into a project management
assistant. It follows PMI's five Process Groups and ten Knowledge Areas, with a practical
working style: rich context, stated output format and audience, reasoning over lookup,
paste-the-data-in, and human judgement on the political calls.

> **Not affiliated with Anthropic.** This is an independent, community-made boilerplate.
> "Claude" and "Claude Code" are products of Anthropic; this project is not endorsed by,
> sponsored by, or otherwise affiliated with Anthropic. "PMI" and "PMBOK" are trademarks of
> the Project Management Institute, which does not endorse this project either.

## Quick start
1. Fill in **`project-context.md`** at the repo root (Claude reads it automatically). To
   write steering reports in French or German while you work in English, set
   **Artifact language**.
2. Use a slash command, e.g. `/charter`, `/risk-register`, `/status-report`.
3. Optionally copy the `project-status.md` template to the repo root and keep your current
   progress, milestones, and budget there — `/status-report` and `/weekly-monday` read it.
4. For an independent second look at a saved artifact, ask for a specialist agent (e.g.
   "have the risk-manager review the register"). Agents review; commands draft.

## What's inside

```
.claude/
├── CLAUDE.md                 # Project context block + working principles (auto-loaded)
├── settings.json             # Permissions (edits limited to docs/ and the two project files)
├── agents/                   # Read-only reviewers for a second pass on saved artifacts
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
│   ├── issue-log.md          /issue-log        → Issue log
│   ├── decision-log.md       /decision-log     → Decision log
│   ├── import-project.md     /import-project   → Onboard an in-flight project
│   ├── project-check.md      /project-check    → Audit setup / import readiness
│   ├── sprint-planning.md    /sprint-planning  → Iteration / sprint plan (agile)
│   ├── backlog-refinement.md /backlog-refinement → Backlog readiness check (agile)
│   ├── retro.md              /retro            → Iteration retrospective (agile)
│   └── pi-planning-prep.md   /pi-planning-prep → Increment / PI planning prep (agile)
└── skills/                   # Methodology packs (auto-trigger on matching tasks)
    ├── pmi-project-management/  # Life-cycle frame + templates/ (17 templates, the single source for structure)
    ├── risk-management/
    ├── stakeholder-management/
    ├── status-reporting/
    ├── change-control/
    └── agile-delivery/         # Methodology-agnostic: Scrum / Kanban / hybrid
```

## Mapping to PMI

| Process Group | Commands |
|---|---|
| Initiating | `/charter`, `/stakeholder-analysis` |
| Planning | `/risk-register`, `/raci`, `/comms-plan`, `/requirements-review` |
| Executing | `/agenda`, `/minutes`, `/escalation` |
| Monitoring & Controlling | `/status-report`, `/change-request`, `/issue-log`, `/decision-log`, `/weekly-monday`, `/weekly-friday` |
| Closing | `/lessons-learned`, `/closure` |
| Setup / any phase | `/import-project` (onboard an in-flight project), `/project-check` (audit it's correctly set up) |
| Agile delivery (methodology-agnostic) | `/sprint-planning`, `/backlog-refinement`, `/retro`, `/pi-planning-prep` |

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
4. Run **`/project-check`** to see what's present, missing, stale, or inconsistent. It also
   proposes `project-context.md` values that your existing docs already state. Then let
   the suggested commands backfill the gaps.

## Ground rules Claude follows
- Never reads live Jira/budgets/Project — **paste the data in**.
- Never fabricates numbers or dates — unknowns are marked `[TBC]`.
- Separates facts from PM judgement, and flags political/stakeholder calls for you.
- Every artifact is a **draft for human review** before it reaches a sponsor or client.
- Follows the data-governance note in `project-context.md`; reminds you to check policy if it's empty.
- Reads the existing file before updating an artifact, and shows what changes before replacing it.
- Ends every draft with a **ready-to-send check**: the checklist at the end of the template,
  reported item by item with failures first. Set **Ready-to-send checks** to `off` in
  `project-context.md` to skip it; `/project-check` still runs the checklists.
- Derives RAG and risk severity from the tolerances and scale in `project-context.md` (kit
  defaults otherwise, labelled as PM judgement).
- Writes saved artifacts in the **Artifact language** from `project-context.md` (the
  language you write in, if it is unset) and keeps talking to you in your own language.
  `[TBC]`, IDs such as `CR-NNN`, file names, dates, and figures never change.

Generated artifacts are suggested into `docs/` (e.g. `docs/charter.md`,
`docs/risk-register.md`, `docs/status/`, `docs/meetings/`, `docs/changes/`,
`docs/sprints/`).

> **Using this for a real project?** `docs/` and `project-status.md` are not git-ignored.
> Work in a private copy, or add them to `.gitignore`, before committing real project data
> to a repo with a public remote.

## Roadmap
A methodology-agnostic agile delivery set (iteration planning, backlog refinement,
retrospectives, increment/PI planning prep) is now included. Remaining planned PMI
additions (WBS, schedule, cost/EVM, quality, resource, procurement, gate
reviews) are tracked in [`ROADMAP.md`](ROADMAP.md).

## License
Released under the [MIT License](LICENSE).
