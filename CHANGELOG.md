# Changelog

What changed in each release of PM Kit. Version numbers follow the `version` in
`.claude-plugin/plugin.json`:

- **Patch** (1.0.**x**) — fixes and wording; nothing for you to do.
- **Minor** (1.**x**.0) — new artifacts, commands, or fields; existing files keep working.
- **Major** (**x**.0.0) — you need to act, e.g. re-run `/project-init` or rename files.

**Plugin install:** update with `/plugin update pm-kit@pm-claude-kit`, start a new session,
and run `/pm-kit:project-init` to see what changed in `CLAUDE.md` and the permissions.
**Clone:** pull the new version; the notes below say if anything needs your attention.

## 1.0.0 — 2026-11-11

The first numbered release, and the first that installs as a Claude Code plugin.

### Added
- **Plugin install.** `/plugin marketplace add fludo/pm-claude-kit`, then
  `/plugin install pm-kit@pm-claude-kit`. As a plugin, commands carry the `pm-kit:` prefix
  (`/pm-kit:status-report`). Cloning the repo still works as before, without the prefix.
- **`/project-init`** — sets up a project folder after a plugin install: copies
  `project-context.md`, `CLAUDE.md`, the permissions, and the `docs/` folders. It creates
  what is missing and never overwrites a file without showing the change and asking.
  Run it again after an update to see what changed.
- **Artifact language** — a new `project-context.md` field. Saved documents are written in
  that language (e.g. French steering reports) while Claude keeps talking to you in yours.
  `[TBC]`, IDs such as `CR-001`, file names, dates, and figures never change. Leave it
  blank to write documents in the language you use with Claude.
- **Ready-to-send checklist** at the end of every template — a few pass/fail checks to tick
  before a document goes to a sponsor or client. After drafting, commands report each
  item, failures first. A `[TBC]` never fails a check; it only has to be listed under the
  document's open questions.
- **Ready-to-send checks** — a new `project-context.md` field. Set it to `off` to skip the
  checklist report after each draft.
- An open-questions section in the closure, lessons-learned, retrospective, and
  stakeholder register templates.

### Changed
- `/project-check` runs each document's checklist from its template and keeps the checks
  that compare documents with each other. It reports the two new fields without treating
  them as gaps, and points to `/project-init` when a project is not set up.
- The reviewer agents run the document's checklist first, write proposed wording in the
  Artifact language, and say so if they cannot read a checklist instead of making one up.
- The permissions in `.claude/settings.json` also allow reading the installed kit's own
  files (read-only), so templates open without a prompt.

### If you use a clone
- `project-context.md` has two new optional fields, **Artifact language** and
  **Ready-to-send checks**. If pulling clashes with your filled-in copy, keep your values
  and add the two lines. Without them, documents follow the language you write in and the
  checklist report stays on.
