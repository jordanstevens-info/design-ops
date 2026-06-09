---
name: work-os-audit
description: >
  Use when the user asks to audit, check, validate, inspect, health-check, or
  find structural/routing/tooling drift in a Work OS folder. This skill is
  read-only and reports findings; it does not apply fixes.
---

# Work OS Audit

Read-only structural and rule compliance inspection for a Work OS folder.
Audit provides evidence. `work-os-reflect` or `work-os:init-os` owns approved
changes after the audit.

## Read Order

1. Root `AGENTS.md`.
2. `context/knowledge/work-os/manifest.json` when present.
3. `personal/AGENTS.md` when personal state matters.
4. Workspace/project routers only when the audit scope names them.
5. Local skill folders: `.agents/skills/` and `.claude/skills/`.
6. `context/feedback/README.md` only when active feedback changes what should
   be checked.

If a routed folder is missing, report it as missing only when the current Work
OS rules require it.

## Checklist

Check:

- Manifest exists and is valid JSON.
- Manifest `workOsVersion` and skill list match installed local skills.
- Every live `AGENTS.md` has a sibling `CLAUDE.md`.
- `AGENTS.md`, `memory.md`, and feedback indexes are under 4,500 characters.
- `.agents/skills/` and `.claude/skills/` are present and synced.
- Required local skills exist: prime, report, feedback, reflect, audit.
- `drop-zone/` and `sandbox/` contain only temporary registered material.
- Structural Work OS changes have nearby log receipts.
- No obvious secret-bearing files are stored in Work OS.
- Unregistered work is flagged, not auto-routed.

Use `rg` for file and text searches. Keep the scan scoped to the target Work
OS; do not inspect unrelated repositories unless the user asks.

## Output

Use this shape:

```text
Audit Summary
- Scope: <root | personal | workspace:<area> | project:<area>/<slug>>
- Result: <pass | needs attention | fail>
- Upgrade: <current | upgrade available | manifest missing | unknown>

Findings
1. <finding>
   Severity: <high | medium | low>
   Evidence: <path or command result>
   Fix route: <reflect | init-os upgrade | feedback | user decision>

Suggested Next Step
<one concise next action>
```

Drop empty sections. Do not write files, create branches, move files, archive
material, or update feedback entries during audit.

## Handoffs

- Version drift or missing bundled skills -> `work-os:init-os upgrade`.
- Structural fixes, receipts, or graduation -> `work-os-reflect`.
- New behavior critique or received signal -> `work-os-feedback`.
- Current-priority orientation -> `work-os-prime`.
- Status or communication drafts -> `work-os-report`.
