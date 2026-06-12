# design-ops

A Claude Code and Codex plugin marketplace for agentic design work.

Design Ops is built for a world where product ideas, prototypes, tickets,
branches, shipped UI, and design-system changes can arrive in any order and
from any discipline. The goal is not to force work back into a linear process.
The goal is to give every artifact a way to be scoped, explored, accepted,
improved, routed, and learned from.

This marketplace currently contains:

- `design` - a generic artifact-loop plugin for product design work.
- `work-os` - a setup plugin for agent-readable workspaces.
- `live-canvas` - a browser canvas for multi-viewport visual review.
- `output-styles` - Claude Code output styles that reshape how the agent responds.

Team-specific variants can fork or wrap these models with local templates,
tools, data rules, and source systems.

## Install

### Claude Code

```shell
claude plugin marketplace add https://github.com/jordanstevens-info/design-ops.git
claude plugin install design@design-ops
claude plugin install live-canvas@design-ops
claude plugin install work-os@design-ops
claude plugin install output-styles@design-ops
```

### Codex

Add the marketplace:

```shell
codex plugin marketplace add https://github.com/jordanstevens-info/design-ops.git
```

Install a plugin:

```shell
codex plugin add design@design-ops
codex plugin add live-canvas@design-ops
codex plugin add work-os@design-ops
```

## Plugins

### design

Design is a generic artifact-loop plugin for product design work. It helps
agents route messy inputs - ideas, prototypes, Figma comps, Jira tickets,
engineer branches, shipped UI, and design-system changes - into the next useful
artifact.

Use it when you want to:

- choose the next design move from unclear input
- scope a problem, research plan, QA plan, or competitive scan
- prototype a coded option study or product facsimile
- make production-code design changes with branch and test discipline
- run design-system evals, acceptance scenarios, or design reviews
- package Jira updates, MRs, demos, presentations, or team updates

#### How To Start

Use `workflow` when the route is unclear:

```text
Use Design workflow to help me choose the next design move.
```

Use focused skills when the next move is known:

```text
Use Design to scope this problem.
Prototype this idea as a coded option study.
Evaluate this prototype against the design system.
Review this MR for design acceptance.
Package this design branch for an MR.
```

#### Artifact Loop

```text
input artifact
-> workflow run
-> output artifact
-> eval or review
-> validation when needed
-> feedback
-> next run
```

Ideas can stay lightweight in `.design/ideas.md` or a local `ideas.md`.
Evidence-bearing work can promote into scope, prototype, eval, ticket, MR,
demo, or presentation artifacts.

Every workflow checks data handling before processing source material. Known or
suspected C4 data stops as `Prohibited`.

#### Skills

- `workflow` - route unclear work and choose the next skill
- `scope` - design scopes, research plans, QA plans, competitive scans
- `prototype` - coded option studies and product facsimiles
- `engineer` - production-code design changes with verification
- `eval` - design-system evals, acceptance scenarios, smoke/quick/full evals
- `review` - MRs, branches, prototypes, tickets, Figma/static designs
- `create-backlog` - backlog-ready ticket content
- `create-mr` - MR title, body, file list, and test plan
- `create-demo` - async walkthrough package and feedback ask
- `create-preso` - design story package, one-pager, outline, demo script
- `slack-update` - copy-pasteable team updates

The plugin exposes focused skills, not command shims. Shared references define
the artifact loop, ideas, data handling, design-system acceptance, and
`.design/` bootstrap.

### work-os

Work OS is a local, file-backed operating model for agent-routed work. It gives
agents a stable place to find goals, tasks, scopes, feedback, knowledge, logs,
source maps, and routing rules across sessions.

Use it when you want:

- continuity across agent sessions
- local context that links out to Jira, Confluence, Figma, Git, and repos
- proposal-first routing for new information and system changes
- read-only audits for drift in skills, manifests, routers, and workspace hygiene

It is not a task app or a replacement for external source systems. It is the
local context layer around them.

#### How To Start

```text
Use Work OS init-os to set up this folder.
Use Work OS init-os to audit this folder before setup.
Use Work OS init-os to upgrade this Work OS.
```

`work-os:init-os` is the only marketplace-facing skill. It checks Git state,
proposes branch-backed setup or upgrade work, writes
`context/knowledge/work-os/manifest.json`, and installs local daily-use skills
into `.agents/skills/` and `.claude/skills/`.

#### Shape

```text
AGENTS.md
CLAUDE.md
context/       knowledge, logs, templates
drop-zone/     raw intake
sandbox/       drafts and experiments
personal/      solo goals, tasks, feedback
workspaces/    durable areas of work
.agents/skills/
.claude/skills/
```

#### Workspaces

`workspaces/` is the cross-repo layer. A workspace can represent a product,
team, client, system, or practice, even when the code lives elsewhere.

```text
workspaces/design-system/
  AGENTS.md
  projects/multi-framework-monorepo/scope.md
  log/

/path/to/design-system-repo/
  AGENTS.md
  packages/
```

Agents start in Work OS to understand priorities and routing, then move into the
implementation repo and follow that repo's own rules. Work OS keeps continuity;
the repo stays the source of truth for code.

#### Local Skills

- `work-os-prime` - read-only orientation
- `work-os-report` - sourced reports and communication drafts
- `work-os-feedback` - signal intake and routing
- `work-os-reflect` - session learning and approved maintenance
- `work-os-audit` - read-only structural health checks

Audit is the diagnostic primitive. Feedback and reflect can use audit findings;
`init-os` owns setup and upgrade writes.

### live-canvas

An infinite canvas with live iframe artboards of your running dev server at multiple viewports and branches.

#### `/live-canvas`

- Compare responsive layouts across breakpoints (desktop, tablet, mobile)
- Visually diff branches side-by-side using git worktrees
- Walk through user flows across multiple routes
- Annotate with sticky notes and callout markers
- Tweak design tokens (colors, spacing, typography) with live hot-reload
- Embed local files (images, video, audio, code) alongside live artboards

### output-styles

A collection of Claude Code output styles. Output styles replace the
output-style portion of the system prompt rather than adding to session context
like a prompt, command, or skill. They are always on, toggleable mid-session,
and do not change how Claude writes code - only how it responds to you. This
plugin is Claude Code only; Codex does not support output styles.

#### Styles

- `be-brief` - terse, fragment-pattern replies with auto-clarity for security
  warnings, irreversible actions, and ambiguous multi-step sequences. Code,
  commits, and PRs stay normal.

#### How To Start

Activate a style with `/config`, then select it under Output style:

```text
/config
```

The selection is saved to `.claude/settings.local.json` as `outputStyle`. It
takes effect on the next session or after `/clear`. You can also drop a style
straight into `~/.claude/output-styles/` or a project's `.claude/output-styles/`
to try it without installing the plugin.

#### Credits

`be-brief` adapts the auto-clarity and boundary sections from
[caveman](https://github.com/JuliusBrussee/caveman) by
[JuliusBrussee](https://github.com/JuliusBrussee) (MIT), reduced to a single
primary instruction. Inspired by
[this video](https://youtu.be/wijoYNiZq3M) comparing caveman to simply adding
"be brief" to a prompt. Source skill:
[caveman SKILL.md](https://github.com/JuliusBrussee/caveman/blob/main/plugins/caveman/skills/caveman/SKILL.md).
