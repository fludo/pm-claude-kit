---
name: agile-delivery
description: Methodology-agnostic agile delivery support — iteration/sprint planning, backlog refinement, retrospectives, and increment/PI planning prep. Use when the task mentions sprint, iteration, backlog, refinement/grooming, retro/retrospective, standup, velocity, story points, definition of done/ready, increment or PI planning, Scrum, or Kanban. Complements the PMI pack; does not commit to any single framework (Scrum, Kanban, SAFe).
---

# Agile Delivery

A light, framework-agnostic set of agile ceremonies. It works for Scrum, Kanban, or a
hybrid — read the `Methodology:` field in `project-context.md` and use the team's own
terms. Treat these as **synonyms**, not different concepts:

- **Iteration = sprint = cycle** — a fixed timebox of delivery.
- **Backlog refinement = grooming = backlog review** — making items ready.
- **Retrospective = retro** — inspect-and-adapt on how the team worked.
- **Increment / PI / quarter planning** — looking ahead across several iterations.

## Discipline (same as the PMI pack)
- **Never invent** velocity, estimates, capacity, or dates. Mark gaps `[TBC]` and ask.
- Everything produced is a **draft for human review**; the team owns the commitment.
- Facts (from the data pasted in) stay separate from PM judgement (labelled).

## The four ceremonies
1. **Iteration/sprint planning** — a goal, capacity, and a *proposed* (not committed)
   selection of backlog items against a definition of done. → `/sprint-planning`
2. **Backlog refinement** — check items are *ready*: clear, estimated, small enough,
   with acceptance criteria. Reuse the `requirements-analyst` agent for wording quality.
   → `/backlog-refinement`
3. **Retrospective** — a fast, action-oriented inspect-and-adapt for one iteration.
   Lighter and more frequent than `/lessons-learned` (which is project/phase-level, by
   knowledge area). → `/retro`
4. **Increment / PI planning prep** — objectives, cross-team dependencies, risks, and
   capacity for the next several iterations. → `/pi-planning-prep`

## Reuse, don't duplicate
- Meeting facilitation / notes → `meeting-scribe` agent.
- Requirement/story wording quality → `requirements-analyst` agent.
- Risks surfaced in planning → `/risk-register` and the `risk-manager` agent.

For PMI mapping these mostly serve **Scope** and **Schedule** in Planning, and
**Integration** in Monitoring & Controlling — but lead with the team's agile language.
