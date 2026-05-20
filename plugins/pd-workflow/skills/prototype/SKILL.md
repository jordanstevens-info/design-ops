---
name: prototype
description: >
  Create or revise coded prototypes, production facsimiles, option studies, or
  repo-backed prototype artifacts for learning and evaluation. Use for trying a
  flow or interaction before production commitment. Do not use for production
  code implementation, MR packaging, backlog ticket writing, or design review.
---

# Prototype

Create a coded artifact for learning. It may be disposable, production-like, or
repo-backed.

Read:

- `../../references/prototype-work.md`
- `../../references/context-bootstrap.md` only in repo-backed mode
- `../../references/agent-roles.md` when using `prototype-designer`

Mode rule:

- Explicit `--sandbox` means sandbox prototype.
- Explicit `--in-repo` means repo-backed prototype.
- If `.design/` exists, default to repo-backed.
- If app repo signals exist but `.design/` does not, ask sandbox or in-repo.
- If no repo/app signals exist, default to sandbox.

Always state the chosen mode and label fake data, shortcuts, missing states, and
production gaps.
