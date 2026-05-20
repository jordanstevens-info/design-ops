# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repo Purpose

Claude Code and Codex plugin marketplace. No build, no app runtime — content is plugin manifests, skills, shared references, and templates loaded by the host CLI on install.

## Layout

- `.claude-plugin/marketplace.json` — Claude Code marketplace manifest. Each `source` path must exist under `plugins/`.
- `.agents/plugins/marketplace.json` — Codex marketplace manifest. Entries use `source.source`, `source.path`, `policy`, and `category`.
- `plugins/<plugin>/.claude-plugin/plugin.json` — Claude plugin manifest.
- `plugins/<plugin>/.codex-plugin/plugin.json` — Codex plugin manifest with richer interface metadata.
- `plugins/<plugin>/skills/<skill>/SKILL.md` — skill definition with YAML frontmatter (`name`, `description` for trigger matching).
- `plugins/<plugin>/references/` — shared workflow doctrine.
- `plugins/<plugin>/templates/` — artifact templates reused by skills.

## Plugins

- **pd-workflow** — one product design workflow plugin with focused skills for `scope`, `prototype`, `engineer`, `review`, `create-ticket`, `create-mr`, `create-preso`, and `slack-update`. It preserves `.design/` context bootstrapping and keeps detailed doctrine in shared references.
- **live-canvas** — single skill providing an infinite canvas of live iframe artboards (multi-viewport, branch diff via git worktrees).
- **design-engineer** — deprecated and unlisted. Kept temporarily for migration reference only.

## Working in this repo

- Skill triggering depends on the `description:` field in frontmatter. Be specific about when a skill should fire.
- Product design workflows use focused skills, not command shims.
- Keep shared doctrine in plugin-level `references/` and `templates/`.
- Do not package custom agents in plugins unless the host plugin spec adds a supported agent surface. Use optional delegation guidance inside skills instead.
- When adding or removing public plugins, update both root marketplaces.
- After editing a skill or manifest, reinstall and exercise the plugin in the target host CLI.
