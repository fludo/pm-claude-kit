---
description: Turn raw meeting notes or a transcript into minutes with action items
argument-hint: [paste notes or transcript]
---

Turn the notes/transcript into **meeting minutes**.
PMI Process Group: **Executing** · Knowledge Area: **Communications**.

Notes / transcript: $ARGUMENTS

Use the **meeting-scribe** agent's minutes method. Produce:
- Attendees / apologies, date, purpose.
- **Decisions made** (clearly stated).
- **Action items** table: action | owner | due date | status — every action has an owner,
  or is flagged `[owner TBC]`.
- **Open issues / parking lot**.
- **Risks or changes raised** that should flow to the risk register or change control.

Be faithful to the source; do not add commitments that were not made. Separate "decided"
from "discussed". Offer to save to `docs/meetings/minutes-YYYY-MM-DD.md`.
