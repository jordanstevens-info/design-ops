---
name: slack-update
description: >
  Draft a copy-pasteable Slack/team update from design workflow context, git
  changes, .design changelog entries, Figma/Jira/Confluence links, or user
  notes. Use only for team communication drafts. Do not auto-publish and do not
  use for tickets, MR packages, presos, reviews, prototypes, engineering, or
  processing C4 data.
---

# Slack Update

Write a team update the user can review, edit, and post themselves.

Path resolution: resolve relative reference and template paths from the
directory containing this `SKILL.md`. If a host installs or exposes this skill
from a rewritten location, locate the nearest parent that contains both
`references/` and `templates/`, then resolve shared assets from that plugin
root.

Read:

- `../../references/artifact-loop.md`
- `../../references/data-handling.md`
- `../../references/communication-work.md`
- `../../references/capability-discovery.md` when source links or tool
  availability affect the update

Use `.design/changelog/` if present. Otherwise fall back to git context, linked
artifacts, and user notes.

Use `../../templates/destination/destination-policy.md` before persisting
drafts. Output inline by default. Do not include the output-contract footer in
the Slack message. If the user asks for a saved communication package, keep any
lineage metadata outside the copy-pasteable message body.

Hard boundary: never send the message through Slack, messaging APIs, webhooks,
or MCP tools. Output copy-pasteable text only.
Stop as `Prohibited` if source material is known or suspected C4.
