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
phase. If the file is missing, that's the top finding.

**2. Expected artifacts by phase**
Based on the current phase, check `docs/` for the artifacts that should exist by now
(earlier-phase artifacts should already be present):

| Phase reached | Expected in `docs/` |
|---|---|
| Initiating | `charter.md`, `stakeholders.md` (initial) |
| Planning | + `risk-register.md`, `raci.md`, `comms-plan.md`, requirements |
| Executing | + at least one `status/` report, `meetings/` records |
| Monitoring & Controlling | + recent `status/` report, `changes/` log if any CRs |
| Closing | + `lessons-learned.md`, `closure.md` |

Mark each **Present / Missing / Empty (placeholder only)**.

**3. Internal consistency & quality**
For the artifacts that exist, spot-check:
- **Risk register** — every risk has an owner, probability, impact, and response; count `[TBC]`.
- **RACI** — exactly one **A** per row; at least one **R** per row.
- **Status report** — has a RAG with a stated rationale and a report date.
- **Stakeholders** — each has a desired engagement level and a key message.
- **Charter** — scope has explicit exclusions; objectives have success measures.
- **Cross-doc** — stakeholders named in the charter appear in the stakeholder register;
  top charter risks appear in the risk register.

**4. Freshness**
Flag the newest `docs/status/` report if it looks stale for the reporting cadence in the
context block (e.g. weekly cadence but newest report > 2 weeks old). Use file dates /
report dates only — do not guess.

**5. Placeholder & fabrication scan**
Count unresolved `[TBC]` markers and any remaining template angle-bracket prompts
(`<...>`) across `docs/`, so the user knows what still needs real data.

## Output

1. **Overall readiness:** 🟢 Ready / 🟡 Partial / 🔴 Not set up — one-line rationale.
2. **Checklist table:** item | status (✅ / ⚠️ / ❌) | note.
3. **Top gaps to fix** — ordered, each with the command that fixes it
   (e.g. "No risk register → run `/risk-register`").
4. **Open questions** — anything only the PM can confirm.

End by offering to action the top gaps (fill context fields, scaffold missing docs, etc.)
on the user's go-ahead. Never fabricate data to make a check pass.
