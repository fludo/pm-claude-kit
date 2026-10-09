---
description: Build a RACI responsibility assignment matrix
argument-hint: [list of activities and roles, or a brief]
---

Build a **RACI matrix** (Responsible, Accountable, Consulted, Informed).
PMI Process Group: **Planning** · Knowledge Area: **Resource**.

Input: $ARGUMENTS

Produce a table with activities/deliverables as rows and roles as columns, each cell
marked R / A / C / I. Rules to enforce and flag if violated:
- Exactly **one A** per row (single point of accountability).
- At least one **R** per row.
- Avoid overloading any role; flag rows with too many C's.

After the table, list:
- **Validation flags** — rows breaking the rules above.
- **Open questions** — roles or activities that need confirmation.

If roles/activities aren't given, derive a starter set from the project context and label
it as a draft to confirm. Offer to save to `docs/raci.md`.
