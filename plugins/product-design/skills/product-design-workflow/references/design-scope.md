# Design Scope

`/scope` creates a shareable design planning artifact. It is not a PRD.

## Scope Types

- **Design scope:** problem, users, goals, non-goals, constraints, open questions, decision needed.
- **Research plan:** assumptions, research questions, method, signals, participants or source material.
- **QA plan:** scenarios, states, breakpoints, accessibility checks, content edge cases, owner questions.
- **Competitive-analysis brief:** comparison set, evaluation dimensions, evidence needed, design implications.
- **Team plan:** what design will do, what PM/engineering/QA need, artifacts to produce, decision points.

## Quality Bar

The artifact should make the next design action obvious. Include:

- Problem statement
- Current state or evidence
- Goals and non-goals
- Constraints
- Unknowns
- Recommended next artifact

Use `.design/` context if present. Do not require bootstrap unless the user asks
to scope repo-backed implementation work.
