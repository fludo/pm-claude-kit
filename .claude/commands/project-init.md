---
description: Set up this project folder for the kit — project context, CLAUDE.md, permissions, and docs folders
argument-hint: [optional: leave blank]
---

Set up the current project folder so the kit works here. Needed once after installing the
kit as a plugin, and again after a kit update to see what changed. In a clone of the kit
repo everything is already in place.
Setup · any phase.

Notes (optional): $ARGUMENTS

Work inline in this conversation — do not delegate to a subagent.

The kit's own files are in `${CLAUDE_PLUGIN_ROOT}/`. If that text is unreplaced, the kit is
this repo: there is nothing to copy. Check that the project files below exist, report
anything missing, and go to step 4.

1. **Look first** — for each row, read the kit file and the project file, if it exists.

   | Kit file | Project file |
   |---|---|
   | `${CLAUDE_PLUGIN_ROOT}/project-context.md` | `project-context.md` |
   | `${CLAUDE_PLUGIN_ROOT}/.claude/CLAUDE.md` | `.claude/CLAUDE.md` |
   | `${CLAUDE_PLUGIN_ROOT}/.claude/settings.json` | `.claude/settings.json` |
   | `${CLAUDE_PLUGIN_ROOT}/docs/README.md` | `docs/README.md` |
   | — | an empty `.gitkeep` in each of `docs/status/`, `docs/meetings/`, `docs/changes/`, `docs/sprints/` |

2. **Propose** — show a table: project file | missing → create / same as the kit → no
   change / different → what would change. Then ask for the go-ahead. Rules:
   - Never overwrite. For a file that exists and differs, show the difference and ask
     about that file on its own.
   - `project-context.md` that already exists holds the user's project data: never change
     it here. List its unfilled fields instead.
   - `.claude/settings.json` that already exists: merge. Add the kit's rules it lacks and
     keep every rule the user has; never remove or loosen one. Show the merged file.
   - `.claude/CLAUDE.md` that holds the user's own instructions: propose adding the kit's
     content after them, not replacing them. A `CLAUDE.md` at the project root is left as
     it is — both load.
3. **Write** — once approved, write exactly what was approved. Copy kit files exactly;
   do not reword, translate, or shorten them.
4. **Next steps** — tell the user:
   - Start a new Claude Code session so the new `CLAUDE.md` and permissions take effect.
   - Then fill `project-context.md`, or run `/import-project` for a project already under
     way. Name commands as they appear in this session — `/pm-kit:import-project` when the
     kit is installed as a plugin.
   - `docs/` and `project-status.md` are not git-ignored: keep real project data out of a
     repo with a public remote.
   - After a kit update, run this command again to see what changed in the kit's
     `CLAUDE.md` and `settings.json`.
