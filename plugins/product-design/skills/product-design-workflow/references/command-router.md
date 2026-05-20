# Command Router

The public commands are explicit task entry points. They do not own doctrine;
they select a mode and hand off to `product-design-workflow`.

| User intent | Command/mode | Primary artifact |
|---|---|---|
| Figure out the design work | `/scope` | Scope, research, QA, competitive, or team plan |
| Try an idea | `/prototype` | Sandbox, facsimile, or repo-backed prototype |
| Change real product code | `/engineer` | Verified `design/<topic>` branch |
| Evaluate an artifact | `/review` | Findings and acceptance/readiness summary |
| Write dev backlog work | `/create-ticket` | Jira/backlog ticket |
| Prepare code for review | `/create-mr` | MR package and pre-filled URL |
| Tell the design story | `/create-preso` | Preso package |
| Share progress | `/slack-update` | Copy-paste update |

## Non-Linear Flow

Design work is not a phase ladder. Route based on the task right now:

- Prototype may lead to ticket, MR, review, or preso.
- Engineer may lead back to prototype if the production constraint changes the idea.
- Review may lead to engineer fixes, ticket edits, or a preso decision ask.
- Scope may be created before, during, or after prototype work.

## Boundaries

- `/engineer` stops at verified design branch work and must not suggest MR work mid-flow.
- `/create-mr` begins only when the user explicitly asks to create the MR package.
- `/review` classifies the target before reviewing.
- `/scope` is design-owned planning; route broad PM discovery or PRDs to the PM plugin seam.

## Ambiguity

Ask one question when the artifact is unclear:

> What should I review: MR, branch, ticket, prototype, Figma/static design, or another designer's work?

For `/prototype`, use the prototype mode rule in `prototype-work.md`.
