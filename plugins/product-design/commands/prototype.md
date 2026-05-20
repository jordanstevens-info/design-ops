---
description: Create or revise a coded prototype.
---

# /prototype

Create or revise a coded prototype.

## Arguments

- `prompt`: prototype goal, route, flow, or option to explore
- `--sandbox`: force a disposable sandbox prototype
- `--in-repo`: force a repo-backed prototype

## Workflow

Route to `product-design-workflow` in prototype mode. Explicit flags win. Without a flag, `.design/` means repo-backed by default; app repo signals without `.design/` require asking sandbox vs in-repo; no repo signals defaults to sandbox.

## Output

A sandbox prototype, production facsimile, or repo-backed prototype artifact with fake data and shortcuts clearly marked.
