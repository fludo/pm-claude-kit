# Project Documents

Generated project artifacts land here. Commands suggest these locations by default:

| Artifact | Default path |
|----------|--------------|
| Charter / PID | `docs/charter.md` |
| Risk register | `docs/risk-register.md` |
| RACI matrix | `docs/raci.md` |
| Communications plan | `docs/comms-plan.md` |
| Stakeholder register | `docs/stakeholders.md` |
| Status reports | `docs/status/status-YYYY-MM-DD.md` |
| Requirements | `docs/requirements.md` |
| Meeting agendas | `docs/meetings/agenda-YYYY-MM-DD.md` |
| Meeting minutes | `docs/meetings/minutes-YYYY-MM-DD.md` |
| Change requests | `docs/changes/CR-NNN.md` |
| Issue log | `docs/issue-log.md` |
| Decision log | `docs/decision-log.md` |
| Sprint plans & retros | `docs/sprints/sprint-NN-plan.md`, `docs/sprints/sprint-NN-retro.md` |
| Increment / PI prep | `docs/sprints/increment-NN-prep.md` |
| Lessons learned | `docs/lessons-learned.md` |
| Closure summary | `docs/closure.md` |

Current status data you maintain yourself lives in `project-status.md` at the repo root
(template in `.claude/skills/pmi-project-management/templates/`). Dates in filenames matter:
`/project-check` and the status commands use them to find the newest file.

These files are **not git-ignored**. Before committing real project data, make sure the
repo's remote is private or add `docs/` content and `project-status.md` to `.gitignore`.

Everything here is a **draft for human review** — verify facts, figures, and dates before
anything reaches a sponsor, client, or steering committee.
