# pd-plugins

A Claude Code and Codex plugin marketplace with product design workflow tools.

## Install

### Claude Code

```shell
claude plugin marketplace add https://github.com/jordanstevens-info/js-plugins
claude plugin install pd-workflow@pd-plugins
```

### Codex

Codex uses the repo-local marketplace at `.agents/plugins/marketplace.json`.

## Plugins

### pd-workflow

One product design workflow plugin for non-linear design work across prototypes, real codebases, review, backlog artifacts, MR packages, design stories, and team updates.

**Skills:**

- `scope` — Create designer-owned scope, research, QA, competitive-analysis, or team planning artifacts
- `prototype` — Create sandbox, production-facsimile, or repo-backed coded prototypes
- `engineer` — Work in a real codebase with `.design/` context, branch discipline, verification, tokens, and accessibility checks
- `review` — Route review work across MRs, branches, prototypes, tickets, Figma/static designs, or another designer's work
- `create-ticket` — Convert design artifacts into outcome-focused backlog/Jira tickets
- `create-mr` — Create an MR package: clean review branch, title/body/test plan, optional push, and pre-filled MR URL
- `create-preso` — Create a design story package with one-pager, deck outline, demo script, and feedback questions
- `slack-update` — Compose copy-pasteable team updates without auto-publishing

The plugin exposes focused skills, not command shims. Shared references preserve the old `.design/` bootstrap and templates while adding dual Claude/Codex support and platform-specific agents.

### live-canvas

An infinite canvas with live iframe artboards of your running dev server at multiple viewports and branches.

#### `/live-canvas`

- Compare responsive layouts across breakpoints (desktop, tablet, mobile)
- Visually diff branches side-by-side using git worktrees
- Walk through user flows across multiple routes
- Annotate with sticky notes and callout markers
- Tweak design tokens (colors, spacing, typography) with live hot-reload
- Embed local files (images, video, audio, code) alongside live artboards

### caveman-output-style

Ultra-compressed communication mode based on [caveman](https://github.com/JuliusBrussee/caveman) — cuts output tokens while keeping full technical accuracy. Ships as output styles selectable via `/config` → Output style.

**Levels:**

| Level | What it does |
|-------|-------------|
| **Caveman Lite** | No filler/hedging. Keep articles + full sentences. Professional but tight |
| **Caveman** | Drop articles, fragments OK, short synonyms. Classic caveman |
| **Caveman Ultra** | Abbreviate (DB/auth/config/req/res/fn/impl), strip conjunctions, arrows for causality (X → Y), one word when one word enough |

```shell
claude plugin install caveman-output-style@js-plugins
```

Select a level via `/config` → Output style. Always-on once selected — no skill invocation needed. Switch to Default to turn off.
