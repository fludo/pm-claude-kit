---
name: risk-management
description: Identify, analyse, respond to, and monitor project risks. Use when the task mentions risk, risk register, risk assessment, probability/impact, mitigation, contingency, issues that might arise, or "what could go wrong" — and for near-term risk reviews (what might crystallise in the next few weeks). PMI Knowledge Area: Risk.
allowed-tools: Read(/${CLAUDE_PLUGIN_ROOT}/**)
---

# Risk Management

Follow the four-step PMI cycle:

1. **Identify** across categories (technical, schedule, cost, resource, external,
   regulatory, organisational, stakeholder). Capture both threats and opportunities. Phrase
   each as **cause → event → effect** so it is testable.
2. **Analyse** — Probability × Impact → Severity, using the *Risk scoring* scale in the
   project context or, if none is set, the 1–5 scale and severity bands in the template.
   Use one scale throughout a register. Note the objective threatened.
3. **Respond** — Threats: Avoid/Mitigate/Transfer/Accept. Opportunities:
   Exploit/Enhance/Share/Accept. Give a concrete action and an owner.
4. **Monitor** — an **early-warning indicator** per top risk and a review cadence.

Use the template at `${CLAUDE_PLUGIN_ROOT}/.claude/skills/pmi-project-management/templates/risk-register.md`.
When a register already exists, update it in place: keep IDs, change status rather than
deleting rows. A risk that has occurred becomes *Realised* and moves to the issue log
(`docs/issue-log.md`). After the first pass, actively hunt
for risks commonly missed for the project's sector/technology and list them as "Candidate
risks to confirm". Never present estimated probabilities as if measured. Draft inline; for
a fresh-eyes challenge of a saved register, use the `risk-manager` agent and pass it the
file path. End with "Open questions for the PM".
