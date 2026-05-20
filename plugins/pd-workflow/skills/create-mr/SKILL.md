---
name: create-mr
description: >
  Create an MR package from a completed design branch: clean review branch,
  title, body, test plan, file list, optional push after approval, and prefilled
  MR URL. Use only for packaging code for review. Do not use for engineering
  implementation, deployment, merging, API-created MRs, tickets, or Slack
  updates.
---

# Create MR

Package a design branch for review. Keep the source design branch intact.

Read:

- `../../references/mr-package.md`
- `../../references/codebase-work.md` only for `.design/` branch context

Use template:

- `../../templates/mr/mr-description.md`

Hard boundary: never merge, deploy, or create the MR through a hosting API.
Push only after user approval and provide a prefilled MR URL.
