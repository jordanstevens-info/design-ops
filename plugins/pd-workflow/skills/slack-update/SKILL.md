---
name: slack-update
description: >
  Draft a copy-pasteable Slack/team update from design workflow context, git
  changes, .design changelog entries, Figma/Jira/Confluence links, or user
  notes. Use only for team communication drafts. Do not auto-publish and do not
  use for tickets, MR packages, presos, reviews, prototypes, or engineering.
---

# Slack Update

Write a team update the user can review, edit, and post themselves.

Read:

- `../../references/communication-work.md`

Use `.design/changelog/` if present. Otherwise fall back to git context, linked
artifacts, and user notes.

Hard boundary: never send the message through Slack, messaging APIs, webhooks,
or MCP tools. Output copy-pasteable text only.
