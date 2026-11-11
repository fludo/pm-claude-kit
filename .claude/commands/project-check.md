---
description: Audit that the project is correctly set up / imported — context, artifacts, consistency
argument-hint: [optional: focus area, e.g. "risks" or "context"]
---

Run a **project setup & import health check**. Report whether this project is correctly
configured and whether an imported in-flight project has everything the kit expects.
Do not fix anything in this pass — **report only**, then offer to fix.

Focus (optional): $ARGUMENTS

## Steps

**1. Context block**
Read `project-context.md` (repo root). Check every field is filled, apart from the two
optional ones below — flag any still containing a `<...>` placeholder or left blank.
Confirm **Current phase** is set to a real phase. If `project-context.md` or
`.claude/CLAUDE.md` is missing, the project is not set up: the top finding is to run
`/project-init`. Call out separately if **Status
tolerances**, **Risk scoring**, or the **Data governance note** are unfilled: RAG and risk
severity fall back to kit defaults, and the data-governance reminder keeps firing.

**Artifact language** is optional and never a gap: report it as the language set, or as
"not set — artifacts follow the conversation language". Only if it is not set and the
existing `docs/` files are written in a language other than this conversation's, mention
once that setting it keeps new artifacts in the same language. **Ready-to-send checks** is
likewise never a gap: report it as on (the default when unfilled) or off.

Report the **RAG basis** (Status tolerances) and the **risk scoring basis** (Risk scoring),
each as one of:
- **Project-specific** — the field holds the project's own values.
- **Kit default** — the field says "kit defaults" or "kit default" (these values stay in
  English whatever the Artifact language), or repeats the values
  in `${CLAUDE_PLUGIN_ROOT}/.claude/skills/pmi-project-management/templates/`: the RAG basis comment in
  `status-report.md`, or the scale and severity bands in `risk-register.md`.
- **Unset** — the field is unfilled, so the kit default applies as PM judgement.

Anything but project-specific is ⚠️ in the checklist and a top gap. The fix is to agree
the values and set the field directly, or run `/import-project`.

Also check `project-status.md` (repo root): present or missing, and its "As of" date. It
is optional before Executing; from Executing onward a missing file is a gap.

**1b. Context the docs already state**
For every context field that is unfilled, except Artifact language, look for the value in
`docs/` (the charter header and its governance, constraints, and stakeholder sections are
the usual places). Build a
table: field | proposed value | source (file and section). Propose only values the docs
state outright — never infer one, and leave a field unproposed if the docs conflict or are
silent. If **Current phase** is unfilled but a doc states it, use that phase for step 2 and
label it an assumption.

**2. Expected artifacts by phase**
Based on the current phase, check `docs/` for the artifacts that should exist by now
(earlier-phase artifacts should already be present):

| Phase reached | Expected in `docs/` |
|---|---|
| Initiating | `charter.md`, `stakeholders.md` (initial) |
| Planning | + `risk-register.md`, `raci.md`, `comms-plan.md`, `requirements.md` |
| Executing | + at least one `status/` report, `meetings/` records, `issue-log.md`, `decision-log.md` |
| Monitoring & Controlling | + recent `status/` report, `changes/` log if any CRs |
| Closing | + `lessons-learned.md`, `closure.md` |

Mark each **Present / Missing / Empty (placeholder only)**.

**3. Ready-to-send checks & cross-document consistency**
For each artifact that exists, run the ready-to-send checklist at the end of its template in
`${CLAUDE_PLUGIN_ROOT}/.claude/skills/pmi-project-management/templates/`. For a folder, check its newest file
only. Report the failed items per file, and one line for a file that passes every item.
This step always runs, whatever *Ready-to-send checks* says in the project context.

| File | Template |
|---|---|
| `docs/stakeholders.md` | `stakeholder-register.md` |
| `docs/status/status-*.md` | `status-report.md` |
| `docs/meetings/agenda-*.md`, `docs/meetings/minutes-*.md` | `agenda.md`, `minutes.md` |
| `docs/changes/CR-*.md` | `change-request.md` |
| `docs/sprints/sprint-*-plan.md`, `docs/sprints/sprint-*-retro.md` | `sprint-plan.md`, `retro.md` |
| `project-status.md` (repo root) | `project-status.md` |
| Any other file in `docs/`, e.g. `docs/charter.md` | The template with the same name |

Then the checks that span files, which live only here:
- **Scoring** — risk scores use the *Risk scoring* scale from the project context (or the
  template default when it is unfilled).
- **RAG basis** — the newest status report's rationale uses the *Status tolerances* from
  the project context, or is labelled PM judgement when they are unfilled.
- **Risks ↔ issues** — risks marked *Realised* have a matching issue in the issue log.
- **Owners** — owners named in the risk register and issue log appear in the stakeholder
  register.
- **Charter ↔ registers** — stakeholders named in the charter appear in the stakeholder
  register; top charter risks appear in the risk register.
- **Minutes ↔ decision log** — decisions recorded in the minutes appear in the decision log.
- **Language** — if Artifact language is set, list `docs/` files written in another
  language (⚠️). Translating one needs the PM's go-ahead.

**4. Freshness**
Flag the newest `docs/status/` report if it looks stale for the reporting cadence in the
context block (e.g. weekly cadence but newest report > 2 weeks old). Do the same for the
"As of" date in `project-status.md`. Use only the date in the filename
(`status-YYYY-MM-DD.md`) or in the report header — file modification times are not
available. If neither carries a date, report "date unknown" rather than guessing.

**5. Placeholder & fabrication scan**
Count unresolved `[TBC]` markers and any remaining template angle-bracket prompts
(`<...>`) across `docs/` and `project-status.md`, so the user knows what still needs real data.

## Output

1. **Overall readiness:** 🟢 Ready / 🟡 Partial / 🔴 Not set up — one-line rationale.
2. **Proposed context block** — the table from step 1b, if any field can be filled from
   the docs, followed by the fields only the PM can supply.
3. **Checklist table:** item | status (✅ / ⚠️ / ❌) | note.
4. **Top gaps to fix** — ordered, each with the command that fixes it
   (e.g. "No risk register → run `/risk-register`").
5. **Open questions** — anything only the PM can confirm.

End by offering to action the top gaps on the user's go-ahead — first of all, writing the
proposed context values into `project-context.md` — then scaffolding missing docs. Never fabricate data to make a check pass.
