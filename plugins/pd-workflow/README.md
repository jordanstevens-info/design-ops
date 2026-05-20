# PD Workflow

PD Workflow is the core workflow plugin for product designers working inside
and outside production codebases. It supports non-linear work: scoping,
prototyping, engineering, review, ticket creation, MR packaging, design story
presos, and team updates.

## Skills

- `scope`: create designer-owned scope artifacts, research plans, QA plans, or
  competitive analysis.
- `prototype`: create or revise sandbox, production-facsimile, or repo-backed
  prototypes.
- `engineer`: work in the real codebase with `.design/`, branch discipline,
  verification, tokens, accessibility, and changelog.
- `review`: classify the target first, then review MRs, branches, prototypes,
  tickets, Figma/static work, or another designer's work.
- `create-ticket`: create a backlog/Jira-ready ticket from design artifacts.
- `create-mr`: create an MR package from a design branch. It does not merge,
  deploy, or create an MR through an API.
- `create-preso`: create a design story package under `.design/presos/<topic>/`
  when repo-backed.
- `slack-update`: write a copy-pasteable update. It never auto-publishes.

## Workflow Model

The public surface is eight focused skills. Shared doctrine lives in
`references/` and artifact templates live in `templates/`.

`.design/` remains the durable branch context layer for codebase-backed design
work. Sandbox prototypes and non-repo scope work can run without it.

## Marketplace Support

This plugin supports both host surfaces:

- Codex: `.codex-plugin/plugin.json` plus `.agents/plugins/marketplace.json`.
- Claude: `.claude-plugin/plugin.json` plus `.claude-plugin/marketplace.json`.

The plugin packages skills, references, and templates only. It does not package
custom agents, so Claude and Codex expose the same workflow shape. Skills may
suggest optional subagent delegation when the host runtime supports it, but no
workflow depends on delegation being available.
