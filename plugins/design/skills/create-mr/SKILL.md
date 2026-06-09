---
name: create-mr
description: >
  Create an MR package from a completed design branch: clean review branch,
  title, body, test plan, file list, optional push after approval, and prefilled
  MR URL. Use only for packaging code for review. Do not use for engineering
  implementation, deployment, merging, API-created MRs, tickets, or Slack
  updates. Do not process C4 data.
---

# Create MR

Package a design branch for review. Keep the source design branch intact.

Path resolution: resolve relative reference and template paths from the
directory containing this `SKILL.md`. If a host installs or exposes this skill
from a rewritten location, locate the nearest parent that contains both
`references/` and `templates/`, then resolve shared assets from that plugin
root.

Read:

- `../../references/artifact-loop.md`
- `../../references/data-handling.md`
- `../../references/mr-package.md`
- `../../references/capability-discovery.md` when GitHub, GitLab, or Git remote
  availability affects packaging
- `../../references/codebase-work.md` only for `.design/` branch context

Use templates:

- `../../templates/mr/mr-description.md`
- `../../templates/output/output-contract.md` for non-trivial outputs
- `../../templates/destination/destination-policy.md` before pushing branches
  or publishing, mutating, or creating remote artifacts

Hard boundary: never merge, deploy, or create the MR through a hosting API.
Push only after explicit approval in the current run and provide a prefilled MR
URL.
Output copy-pasteable MR title and description without an output-contract
footer in the MR body. Keep package lineage metadata separate when useful:
destination decision, actor/authority fields, stop condition, feedback/rerun
path, and next action.
Stop as `Prohibited` if source material is known or suspected C4.
