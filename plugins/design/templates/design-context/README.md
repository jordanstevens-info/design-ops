# [Project Name]

[One-line description — from repo CLAUDE.md, README, or interview]

## Design Context

**Branch:** `design/[feature-name]`
**Figma:** [URL if known, otherwise omit this line]
**Scope:** [What this design branch is implementing]
**Resonant Frequency:** [Frequency from vision or scope if known, otherwise omit this line]

## Knowledge Sources

Sources resolved during `.design/` bootstrap. **Found** = referenced from repo.
**Created** = generated in `.design/knowledge/` from templates.

| File | Path | Status |
|------|------|--------|
| Vision | [path or `.design/knowledge/vision.md`] | [found / created] |
| Architecture | [path or `.design/knowledge/architecture.md`] | [found / created] |
| Standards | [path or `.design/knowledge/standards.md`] | [found / created] |
| Design System | `.design/knowledge/design-system.md` | created |
| Context Map | [path or `.design/knowledge/context-map.md`] | [found / created / omitted] |
| Sources | [path or `.design/knowledge/sources.md`] | [found / created / omitted] |
| Tooling | [path or `.design/knowledge/tooling.md`] | [found / created / omitted] |
| Working Agreements | [path or `.design/knowledge/working-agreements.md`] | [found / created / omitted] |

**Repo CLAUDE.md:** [yes — path / no]
**Repo docs:** [list paths found, or "none"]
**Ideas:** [.design/ideas.md if created, otherwise "none captured yet"]

## Commands

```bash
[dev command]      # [description]
[build command]    # [description]
[test command]     # [description]
[lint command]     # [description — omit if not detected]
```

## Working With This Context

Before implementation, read the knowledge sources listed above and apply
`data-handling.md` before processing source material or evidence.

**Read order:** `.design/README.md` (routing + current state) →
`.design/knowledge/` (graduated patterns) → `.design/changelog/` (recent sessions)
→ repo `CLAUDE.md` (implementation)

After working:
- Write a dated entry in `.design/changelog/` (see `templates/changelog-entry.md`)
- Capture lightweight repo-backed ideas in `.design/ideas.md` only when they are
  real possibilities worth revisiting
- Update `.design/knowledge/design-system.md` if new tokens or components were established
- Update `.design/knowledge/standards.md` if new durable standards emerged
