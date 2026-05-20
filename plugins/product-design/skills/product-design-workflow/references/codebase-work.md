# Codebase Work

`/engineer` implements design work in the real repo on a `design/<topic>` branch.

## Principles

- `.design/` is branch-scoped portable context.
- Visual fidelity and accessibility are exit gates.
- Prefer existing modules, components, tokens, and helpers.
- Do not hardcode raw colors, spacing, or fonts when tokens exist.
- Keep scope narrow and remove dead spike code.

## Workflow

1. Bootstrap `.design/` if needed.
2. Read `.design/README.md`, `.design/knowledge/`, and `.design/changelog/`.
3. Inspect existing components, tokens, conventions, and Figma when available.
4. Confirm scope from current branch context.
5. Work bottom-up: tokens, primitives, composed components, page layouts.
6. Verify build/lint/test plus visual, responsive, accessibility, and dead-code gates.
7. Write `.design/changelog/` entry.
8. Graduate durable patterns to `.design/knowledge/design-system.md` or `standards.md`.
9. Update current state in `.design/README.md`.
10. Commit and push the design branch when appropriate.

## Boundary

Stop after verified design branch work. Do not suggest `/create-mr` during this
flow. The user invokes `/create-mr` explicitly.
