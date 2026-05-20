---
description: Write a team update.
---

# /pd-slack-update

Write a team update.

## Arguments

- `source`: optional branch, changelog, ticket, Figma URL, notes, or summary

## Workflow

Route to `product-design-workflow` in communication mode. Use `.design/changelog/` if present, otherwise fall back to git/context supplied by the user.

## Output

A copy-pasteable Slack update. Never auto-publish.
