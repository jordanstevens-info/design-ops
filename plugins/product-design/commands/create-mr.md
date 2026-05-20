---
description: Create an MR package from design branch work.
---

# /create-mr

Create an MR package from design branch work.

## Arguments

- `design_branch`: optional source design branch
- `scope`: optional package scope hint: code only, code plus selected artifacts, or everything

## Workflow

Route to `product-design-workflow` in MR package mode. Read `.design/README.md` and `.design/changelog/`, create a clean review branch, draft title/body/test plan, present file list, push only after approval, and provide a pre-filled MR URL.

## Boundary

Never merge, deploy, or create the MR through a hosting API.
