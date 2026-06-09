---
name: work-os-prime
description: >
  Use when the user asks to prime, orient, start the day/session, find current
  priorities, or decide what to look at next in Work OS.
---

# Work OS Prime

Read-only orientation. Return priorities, blockers, and routing exceptions.
Never create reports, feedback entries, logs, or cleanup proposals.

## Read Order

1. Root `AGENTS.md`.
2. `personal/AGENTS.md` when present.
3. `context/knowledge/README.md` and specific `context/knowledge/work-os/`
   files only when the ask involves structure, routing, skills, templates, or
   graduation.
4. Personal goals and tasks when present: `personal/goals/`,
   `personal/tasks/started/`, `personal/tasks/blocked/`, and relevant
   `personal/tasks/not_started/`.
5. Named team/company workspace router: `workspaces/<area>/AGENTS.md`.
6. Named personal sideproject router:
   `personal/sideprojects/<slug>/AGENTS.md`.
7. Named project `scope.md`, then story, decisions, research, or artifacts only
   when needed.
8. Latest relevant `context/log/`, personal log, workspace log, or project log
   entry when recent history matters.
9. Nearest feedback index only when active feedback changes the likely next
   move.

If a routed folder does not exist, say it is not populated yet. Do not treat
missing earned folders as errors.

## Maintenance Checks

- Flag `AGENTS.md` or `memory.md` files over 4,500 characters.
- Flag any feedback index over 4,500 characters.
- Flag any `AGENTS.md` scope missing a sibling `CLAUDE.md` adapter.
- Flag empty live directories outside `.git/`, `.archive/`, and nested
  repositories.
- Flag unregistered work only when it needs a routing decision.

Do not move, rename, archive, delete, or formalize anything during prime.

## Output Shape

Keep orientation compact:

```text
Prime Summary
- Scope: <root | personal | workspace:<area> | project:<area>/<slug>>

Daily Guidance
1. <best focus item>
   [source](path)
   Note: <why this is the next useful move>

Needs Attention
2. <blocked or in-review item>
   [source](path)
   Next: <unblock or review step>

Triage Items
3. <actual routing/maintenance exception>
   [source](path)
   Note: <decision needed>
```

Number only actionable handles. Drop empty sections. Do not draft structured
reports or communications; that belongs to `work-os-report`. Do not propose
feedback entries; that belongs to `work-os-feedback`. Do not propose log
entries or cleanup actions; that belongs to `work-os-reflect`.
