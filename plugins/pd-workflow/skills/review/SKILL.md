---
name: review
description: >
  Review product design artifacts for design acceptance, readiness, or critique:
  MRs, branches, prototypes, tickets, Figma/static designs, screenshots, or
  another designer's work. Use for design-quality findings and acceptance risk.
  Do not use for broad code review, implementation-only review, scoping,
  prototyping, ticket drafting, or MR package creation.
---

# Review

Classify the target first, then run the appropriate design review.

Read:

- `../../references/review-work.md`
- `../../references/codebase-work.md` only for branch/current-work design QA
- `../../references/mr-package.md` only for MR acceptance context
- `../../references/agent-roles.md` when using `design-reviewer`

Target classes:

- MR or PR: design acceptance review.
- Current branch or design branch: pre-submit design QA.
- Ticket: backlog readiness and acceptance clarity.
- Prototype: design critique and exploration gaps.
- Figma/static design: implementation-readiness and state coverage.
- Another designer's work: critique with feedback questions and risks.

Output findings first, ordered by severity, followed by missing evidence and an
acceptance/readiness/critique summary.
