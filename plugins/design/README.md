# Design

Design is the core workflow plugin for non-linear design work inside and
outside production codebases. It supports scoping, prototyping, engineering,
eval, review, design acceptance, feedback reports, Jira/backlog updates, MR
packaging, async demo packages, design story presos, idea capture, and team
updates. It also carries resonant-frequency framing as a workflow lens for
finding the project thread, metrics, guardrails, and decision rule.

## Skills

- `workflow`: orient open-ended design work, capture ideas, choose a recipe,
  and route into the right next skill.
- `scope`: create designer-owned scope artifacts, research plans, QA plans, or
  competitive analysis.
- `prototype`: create or revise sandbox, production-facsimile, or repo-backed
  prototypes.
- `engineer`: work in the real codebase with `.design/`, branch discipline,
  verification, tokens, accessibility, and changelog.
- `eval`: run design-system evals, acceptance scenarios, smoke/quick/full
  evals, and system-performance checks.
- `review`: classify the target first, then review MRs, branches, prototypes,
  tickets, Figma/static work, or another designer's work.
- `create-backlog`: draft or revise Jira/backlog-ready ticket content from design artifacts.
- `create-mr`: create an MR package from a design branch. It does not merge,
  deploy, or create an MR through an API.
- `create-demo`: create an async demo package with recording outline, demo
  links, feedback questions, and distribution blurb.
- `create-preso`: create a design story package under `.design/presos/<topic>/`
  when repo-backed.
- `slack-update`: write a copy-pasteable update. It never auto-publishes.

## Workflow Model

The public surface is focused skills plus one workflow router. Shared doctrine lives in
`references/` and artifact templates live in `templates/`.

Skill files link to shared assets with paths relative to the directory containing
their `SKILL.md`. If a host installs or exposes a skill from a rewritten
location, resolve shared assets from the nearest parent that contains both
`references/` and `templates/`; do not assume a fixed cache, marketplace, or
version-directory depth.

`.design/` remains the durable branch context layer for codebase-backed design
work. Sandbox prototypes and non-repo scope work can run without it. Every
workflow starts from an artifact state, applies data-handling rules, records the
output and stop condition, and produces a feedback report or rerun instruction
when useful.

Resonant frequency is the qualitative signal that makes the work cohere. The
plugin uses it to connect scope, prototype choices, metrics, guardrails, review
judgment, demos, and presentation stories without turning every output into a
heavy rubric.

Non-trivial runs use a shared output contract and destination policy so skills
agree on source refs, authorship, reviewers, decision owners, evidence, stop
conditions, and where artifacts should live. Design-system evals use acceptance
scenarios as the primary review artifact. Smoke evals stay diagnostic; full
eval, acceptance review, validation findings, and system-performance reports
each have separate templates.

## Marketplace Support

This plugin supports both host surfaces:

- Codex: `.codex-plugin/plugin.json` plus `.agents/plugins/marketplace.json`.
- Claude: `.claude-plugin/plugin.json` plus `.claude-plugin/marketplace.json`.

The plugin packages skills, references, and templates only. It does not package
custom agents, so Claude and Codex expose the same workflow shape. Skills may
suggest optional subagent delegation when the host runtime supports it, but no
workflow depends on delegation being available.
