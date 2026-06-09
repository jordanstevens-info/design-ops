---
name: jira-update
description: >
  Draft or revise Jira/backlog-ready ticket content from existing design
  artifacts, branches, prototypes, Figma links, design stories, or notes. Use
  when the user asks for a Jira update, update Jira, a Jira ticket, a backlog
  update, design-to-backlog, backlog-ready work, rewrite ticket, development
  ticket, or an outcome-focused ticket from design work. Do not use for
  open-ended design scoping, research planning, prototyping, MR packaging,
  review, or processing C4 data.
---

# Jira Update

Draft or revise Jira/backlog-ready ticket content from design artifacts. The
ticket describes the desired product outcome and acceptance criteria without
prescribing implementation.

Path resolution: resolve relative reference and template paths from the
directory containing this `SKILL.md`. If a host installs or exposes this skill
from a rewritten location, locate the nearest parent that contains both
`references/` and `templates/`, then resolve shared assets from that plugin
root.

Read:

- `../../references/artifact-loop.md`
- `../../references/data-handling.md`
- `../../references/capability-discovery.md` when Jira or backlog-tool access is
  relevant
- `../../references/ticket-work.md`
- `../../references/design-scope.md` only when scope context exists
- `../../references/resonant-frequency.md` when source artifacts include a
  project thread, success metric, guardrail metrics, or decision rule

Use templates:

- `../../templates/ticket/jira-ticket.md`
- `../../templates/output/output-contract.md` only when lineage is useful
  outside the ticket body
- `../../templates/destination/destination-policy.md` before creating or
  updating any external ticket

Output the ticket draft, design references used, coverage gaps, and any open
questions that affect acceptance criteria. Consume resonant frequency context by
translating it into normal ticket outcomes, acceptance criteria, success
metrics, constraints, or non-goals; do not add a `Resonant Frequency` section to
the Jira/backlog ticket body. Draft inline by default. Do not include the
output-contract footer in the Jira/backlog ticket body. Create or update
Jira/backlog systems only after an explicit user request and destination-policy
checks. Stop as `Prohibited` if source material is known or suspected C4.
