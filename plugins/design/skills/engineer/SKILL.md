---
name: engineer
description: >
  Make real production-code design changes in a codebase using .design context,
  design branch discipline, build/lint/test verification, design tokens,
  accessibility checks, and changelog updates. Use when the work should become
  mergeable code. Do not use for throwaway prototypes, MR package creation,
  backlog tickets, general code review, or processing C4 data.
---

# Engineer

Work in the real codebase on a `design/<topic>` branch. Maintain `.design/`
context, verify the work, and stop before MR packaging.

Path resolution: resolve relative reference and template paths from the
directory containing this `SKILL.md`. If a host installs or exposes this skill
from a rewritten location, locate the nearest parent that contains both
`references/` and `templates/`, then resolve shared assets from that plugin
root.

Read:

- `../../references/artifact-loop.md`
- `../../references/data-handling.md`
- `../../references/codebase-work.md`
- `../../references/resonant-frequency.md` when a design branch, scope, or
  `.design/knowledge/vision.md` names a project thread or decision rule
- `../../references/design-system-acceptance.md`
- `../../references/capability-discovery.md` when Figma, browser, Storybook,
  Git, or local runtime availability affects verification
- `../../references/context-bootstrap.md`
- `../../references/optional-delegation.md` only for optional read-only
  scouting when the runtime supports it

Use `../../templates/output/output-contract.md` for non-trivial outputs and
`../../templates/destination/destination-policy.md` before persisting reports,
writing external systems, or pushing branches.

Hard boundary: do not create, suggest, or start MR work. That belongs to the
`create-mr` skill only when the user asks for MR packaging.

Output changed files, verification evidence, how the change advances the
resonant frequency when one exists, changelog/design-context updates,
destination decisions, actor/authority fields, stop condition, feedback/rerun
path, next action, and any unresolved design or implementation risks. Stop as
`Prohibited` if the source material is known or suspected C4.
