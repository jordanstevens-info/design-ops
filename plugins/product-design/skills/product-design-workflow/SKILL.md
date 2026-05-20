---
name: product-design-workflow
description: >
  Product design workflow for scoping, prototyping, design engineering,
  review, backlog tickets, MR packages, design story presos, and team updates.
  Use when designers need to decide, explore, implement, evaluate, package, or
  present product design work across coded prototypes and real codebases.
---

# Product Design Workflow

One plugin, one workflow. This skill routes non-linear product design work to
the right artifact without splitting doctrine across many thin skills.

## Public Commands

| Command | Mode | Output |
|---|---|---|
| `/scope` | Scope | Design scope, research plan, QA plan, competitive brief, or team plan |
| `/prototype` | Prototype | Sandbox prototype, production facsimile, or repo-backed prototype |
| `/engineer` | Codebase work | Verified `design/<topic>` branch with `.design/` context |
| `/review` | Review router | MR acceptance, branch QA, prototype critique, ticket readiness, or spec review |
| `/create-ticket` | Ticket | Outcome-focused Jira/backlog ticket |
| `/create-mr` | MR package | Clean review branch, MR title/body/test plan, file list, optional push, prefilled URL |
| `/create-preso` | Design story | Preso package with story, one-pager, deck outline, and demo script |
| `/slack-update` | Communication | Copy-pasteable team update |

Commands are thin entry points. Do not duplicate doctrine in command files.

## Routing Rules

If a command is used, follow that mode. If the user asks naturally, infer the
mode from the artifact and outcome they want. When multiple targets are likely,
ask one concrete question before acting.

Read references only as needed:

- Routing and boundaries: `references/command-router.md`
- Context setup: `references/context-bootstrap.md`
- Codebase work: `references/codebase-work.md`
- Prototypes: `references/prototype-work.md`
- Reviews: `references/review-work.md`
- Scope artifacts: `references/design-scope.md`
- Tickets: `references/ticket-work.md`
- MR packages: `references/mr-package.md`
- Presos: `references/design-story.md`
- Updates: `references/communication-work.md`
- PM seams: `references/pm-seams.md`
- Agent roles: `references/agent-roles.md`
- Agent packaging: `references/agent-packaging.md`
- Marketplace compatibility: `references/dual-marketplace.md`

## Bootstrap Matrix

Bootstrap is not universal.

- `/engineer`: requires `.design/` bootstrap.
- `/review`: requires `.design/` only for branch or MR review.
- `/create-mr`: requires `.design/changelog/` context from a design branch. If missing, ask for context before drafting.
- `/create-ticket`: uses `.design/` if present; does not require it.
- `/create-preso`: uses `.design/` if present; creates `.design/presos/` only for repo-backed work.
- `/prototype`: uses bootstrap only in repo-backed mode.
- `/scope`: uses `.design/` if present; does not require bootstrap.
- `/slack-update`: uses `.design/changelog/` if present; otherwise falls back to git and user context.

When bootstrap is required or selected, run `references/context-bootstrap.md`
before implementation or artifact drafting.

## Prototype Mode

Explicit flags win:

- `/prototype --sandbox`: sandbox prototype.
- `/prototype --in-repo`: repo-backed prototype.

Without a flag:

- `.design/` exists: repo-backed prototype by default.
- App repo signals exist but `.design/` does not: ask sandbox or in-repo.
- No repo/app signals: sandbox prototype by default.

Always state the chosen prototype mode and mark fake data, shortcuts, and
production gaps.

## Hard Boundaries

- `/engineer` stops at verified design branch work. It may commit and push the
  design branch, but it must not suggest or start MR work.
- `/create-mr` creates a package for review. It never merges, deploys, or
  creates an MR through a hosting API.
- `/create-ticket` describes outcomes, not implementation prescriptions.
- `/slack-update` never publishes through Slack or another messaging API.
- `/scope` is design scope. It does not create PRDs or run broad PM discovery;
  see `references/pm-seams.md`.

## Review Contract

`/review` classifies the target first:

- MR or PR: design acceptance review.
- Current branch or design branch: pre-submit design QA.
- Ticket: backlog readiness and acceptance clarity.
- Prototype: design critique and exploration gaps.
- Figma/static design: implementation-readiness and state coverage.
- Another designer's work: critique with feedback questions and risks.

Use `design-reviewer` for the critique pass when delegation is available; the
main workflow owns classification and final formatting.

## Agents

Use agents only for bounded work that benefits from isolation or parallelism.
See `references/agent-roles.md`.

- `codebase-scout`: read-only context gathering.
- `prototype-designer`: prototype/facsimile creation.
- `repo-design-engineer`: real codebase design implementation.
- `design-reviewer`: adversarial design review.
- `artifact-writer`: template-governed communication artifacts.

Codex agent files are TOML. Claude agent files are Markdown. Do not mix formats.

## Output Style

Be direct and artifact-oriented. Name the artifact produced, evidence checked,
and remaining decision needed. When work changes files, include verification
commands or review steps appropriate to the mode.
