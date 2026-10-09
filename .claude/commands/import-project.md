---
description: Import an already-started project — interview, ingest pasted data, and scaffold context + docs
argument-hint: [paste any existing material, or a brief, or leave blank]
---

Onboard an **already-started (in-flight) project** into this kit in one guided pass.
Goal: a filled-in `project-context.md` and a populated `docs/` folder that reflect where
the project **actually is today** — not a fresh Initiating-phase project.

Material provided (optional): $ARGUMENTS

## Step 1 — Interview (ask, don't assume)
If `project-context.md` is already filled, read it and skip what's known. Otherwise ask the
user — in one batched set of questions — for the context block fields:
project name/code, PM role & authority, org/sector, methodology, governance & reporting
cadence, key constraints, primary stakeholders, and **current phase** (the real one).
Also ask: *where does the live project data live?* (Jira, MS Project, spreadsheets,
email/docs) so you know what they can paste.

## Step 2 — Ingest what exists
Accept whatever the user pastes or points to (exports, notes, old status emails, a charter
draft, a task list). **Organise it; never invent.** Sort the material into the kit's
artifacts:

| Source material | Target file |
|---|---|
| Charter / scope / objectives | `docs/charter.md` |
| Risks / issues mentioned | `docs/risk-register.md` |
| Stakeholders / contacts / sponsor | `docs/stakeholders.md` |
| Roles / responsibilities | `docs/raci.md` |
| Latest progress / status email | `docs/status/status-YYYY-MM-DD.md` |
| Meeting notes / decisions | `docs/meetings/` |
| Change requests / variations | `docs/changes/` |

For any artifact with no source material, create a **stub** from the matching template in
`.claude/skills/pmi-project-management/templates/`, filled only with what's known and
`[TBC]` elsewhere — do not fabricate.

## Step 3 — Write the files
1. Write/update `project-context.md` with the interview answers.
2. Create each target `docs/` file above, mapping the ingested material into the template
   structure. Keep cause→event→effect phrasing for risks, success measures for objectives,
   one-A-per-row for RACI, etc.
3. Where the user said data lives in another tool but hasn't pasted it, leave a clear
   `[TBC — paste from <tool>]` marker and list it in the summary.

## Step 4 — Verify
Run the same checks as `/project-check` and output:
- **What was imported** — file-by-file, with a one-line note each.
- **What's still needed** — the `[TBC]` items and which tool/source to pull them from.
- **Suggested next commands** — e.g. `/risk-register` to expand the risk stub,
  `/stakeholder-analysis` to classify stakeholders, `/status-report` for the next cycle.
- **Overall readiness:** 🟢 / 🟡 / 🔴 with a one-line rationale.

## Rules
- Confirm before overwriting any existing `docs/` file — show what would change.
- Everything produced is a **draft for human review**; flag political/stakeholder judgement
  calls for the PM. Never backfill numbers, dates, or decisions that weren't in the source.
