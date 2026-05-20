---
name: engineer
description: >
  Make real production-code design changes in a codebase using .design context,
  design branch discipline, build/lint/test verification, design tokens,
  accessibility checks, and changelog updates. Use when the work should become
  mergeable code. Do not use for throwaway prototypes, MR package creation,
  backlog tickets, or general code review.
---

# Engineer

Work in the real codebase on a `design/<topic>` branch. Maintain `.design/`
context, verify the work, and stop before MR packaging.

Read:

- `../../references/codebase-work.md`
- `../../references/context-bootstrap.md`
- `../../references/optional-delegation.md` only for optional read-only
  scouting when the runtime supports it

Hard boundary: do not create, suggest, or start MR work. That belongs to the
`create-mr` skill only when the user asks for MR packaging.

Output changed files, verification evidence, changelog/design-context updates,
and any unresolved design or implementation risks.
