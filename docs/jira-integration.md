# Jira / Atlassian MCP integration

This kit is a **drafting and reasoning partner, not a system of record**. By default it
never reads live Jira — you paste data in (or keep it in `project-status.md`). This note
explains the optional live integration and the project-wide switch that gates it.

The kit does **not** ship its own Jira connector. It is MCP-*aware*: it recognises a
connected Atlassian MCP server and will use it only when you explicitly grant access.

---

## 1. The access switch

A single project-wide switch decides whether Claude may read live Jira/Confluence. It
lives in `project-context.md`:

```
- **Jira / Atlassian MCP access:** `block`   # or `allow`
```

| Value | Behaviour |
|-------|-----------|
| `block` (default) | Paste-in only. Claude must **not** call any Jira/Atlassian MCP tool, **even if a server is connected**. |
| `allow` | The Jira-aware commands *may* read live from a connected Atlassian MCP. If no server is connected, they fall back to paste-in and say so. |

The switch is **authoritative** and **fail-safe**: a missing, blank, or unclear value is
treated as `block`. The switch overrides the presence of a connected server — connecting a
server does not grant access; flipping this field does.

The semantics are defined once in `.claude/CLAUDE.md` §1 ("Live data sources"). The
commands below reference the switch rather than repeating the rule.

### Commands that honour the switch

- `/status-report`
- `/weekly-monday`
- `/sprint-planning`
- `/backlog-refinement`
- `/pi-planning-prep`

Notes-based commands (`/retro`, `/weekly-friday`, `/minutes`, etc.) are unaffected — they
work from pasted notes, not Jira registers.

---

## 2. Connecting an Atlassian MCP server

Pick an existing, maintained server — do not build one.

- **Atlassian official remote MCP server** — hosted by Atlassian, OAuth sign-in, covers
  Jira and Confluence. Preferred for most users.
- **`sooperset/mcp-atlassian`** — mature community server; supports Jira Cloud/Server/DC
  and Confluence, authenticates with an API token. Useful for self-hosted or Data Center.

Follow the chosen server's own setup instructions to register it as an MCP server in your
Claude client. Connecting it is necessary but **not** sufficient — you must also set the
switch to `allow` (see below).

---

## 3. Turning it on

1. Connect an Atlassian MCP server in your Claude client (step 2).
2. Confirm your organisation's data-handling policy permits live access to the relevant
   Jira project — especially for client-confidential or regulated data.
3. In `project-context.md`, set:
   ```
   - **Jira / Atlassian MCP access:** `allow`
   ```
4. Optionally record which board/project is the source, so reports can cite it.

To turn it off again, set the value back to `block`. The next session will stop reading
live data immediately.

---

## 4. Guardrails that still apply under `allow`

Granting live access does **not** relax the kit's core discipline:

- **No fabricated numbers or dates.** Live-fetched data is real data; if a value is missing
  from Jira, mark it `[TBC]` rather than guessing.
- **Data governance.** The data-handling reminder still applies before pulling
  client-confidential issues.
- **Label the source.** When a command uses a live fetch, it states it in one line
  (e.g. *"Source: live Jira, board NGF, pulled 2026-10-10"*) so the reader knows the
  figures came from Jira, not a paste.
- **Draft for review.** Every artifact remains a draft for human review before it reaches a
  sponsor, client, or steering committee.
