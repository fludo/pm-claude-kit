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
Read `project-context.md` (repo root). Check every field is filled — flag any still
containing a `<...>` placeholder or left blank. Confirm **Current phase** is set to a real
phase. If the file is missing, that's the top finding. Call out separately if **Status
tolerances**, **Risk scoring**, or the **Data governance note** are unfilled: RAG and risk
severity fall back to kit defaults, and the data-governance reminder keeps firing.

Report the **RAG basis** (Status tolerances) and the **risk scoring basis** (Risk scoring),
each as one of:
- **Project-specific** — the field holds the project's own values.
- **Kit default** — the field says "kit defaults" or "kit default", or repeats the values
  in `.claude/skills/pmi-project-management/templates/`: the RAG basis comment in
  `status-report.md`, or the scale and severity bands in `risk-register.md`.
- **Unset** — the field is unfilled, so the kit default applies as PM judgement.

Anything but project-specific is ⚠️ in the checklist and a top gap. The fix is to agree
the values and set the field directly, or run `/import-project`.

Also check `project-status.md` (repo root): present or missing, and its "As of" date. It
is optional before Executing; from Executing onward a missing file is a gap.

**1b. Context the docs already state**
For every context field that is unfilled, look for the value in `docs/` (the charter header
and its governance, constraints, and stakeholder sections are the usual places). Build a
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

**3. Internal consistency & quality**
For the artifacts that exist, spot-check:
- **Risk register** — every risk has an owner, probability, impact, and response; scores
  use the scale set in the project context (or the template default), not a mix; count `[TBC]`.
- **RACI** — exactly one **A** per row; at least one **R** per row.
- **Status report** — has a RAG with a stated rationale and a report date; the rationale
  refers to the status tolerances or is labelled PM judgement.
- **Stakeholders** — each has a desired engagement level and a key message.
- **Charter** — scope has explicit exclusions; objectives have success measures.
- **Issue log** — every open issue has an owner, a next action, and a target date; none is
  overdue without being escalated.
- **Decision log** — every decision names who decided it and a source; decisions in the
  minutes appear in the log.
- **Cross-doc** — risks marked *Realised* have a matching issue; owners named in the risk
  register and issue log appear in the stakeholder register.
- **Cross-doc** — stakeholders named in the charter appear in the stakeholder register;
  top charter risks appear in the risk register.

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
