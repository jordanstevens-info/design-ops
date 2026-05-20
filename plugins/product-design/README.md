# Product Design

Product Design is the core workflow plugin for product designers working inside
and outside production codebases. It supports non-linear work: scoping,
prototyping, engineering, review, ticket creation, MR packaging, design story
presos, and team updates.

## Commands

- `/pd-scope`: create designer-owned scope artifacts, research plans, QA plans, or
  competitive analysis.
- `/pd-prototype`: create or revise sandbox, production-facsimile, or repo-backed
  prototypes.
- `/pd-engineer`: work in the real codebase with `.design/`, branch discipline,
  verification, tokens, accessibility, and changelog.
- `/pd-review`: classify the target first, then review MRs, branches, prototypes,
  tickets, Figma/static work, or another designer's work.
- `/pd-create-ticket`: create a backlog/Jira-ready ticket from design artifacts.
- `/pd-create-mr`: create an MR package from a design branch. It does not merge,
  deploy, or create an MR through an API.
- `/pd-create-preso`: create a design story package under `.design/presos/<topic>/`
  when repo-backed.
- `/pd-slack-update`: write a copy-pasteable update. It never auto-publishes.

## Workflow Model

The canonical skill is `skills/product-design-workflow/SKILL.md`. It stays lean
and routes to reference files for doctrine. Commands are thin entry points that
state purpose, inputs, output, and route into the workflow skill.

`.design/` remains the durable branch context layer for codebase-backed design
work. Sandbox prototypes and non-repo scope work can run without it.

## Marketplace Support

This plugin supports both host surfaces:

- Codex: `.codex-plugin/plugin.json` plus `.agents/plugins/marketplace.json`.
- Claude: `.claude-plugin/plugin.json` plus `.claude-plugin/marketplace.json`.

Claude-facing agents live in `agents/claude/*.md`. Codex custom agents live in
`agents/codex/*.toml`. Shared role doctrine belongs in workflow references, not
duplicated across both agent formats.
