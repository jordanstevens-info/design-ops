---
name: work-os-report
description: >
  Use when the user asks for status, reports, weekly updates, standups, 1:1
  prep, goal/project/workspace summaries, tooling/access summaries, Slack or
  email drafts, or doc/MCP-ready output from Work OS context.
---

# Work OS Report

Structured output and communication drafts. Read the right source context,
choose the requested format, and produce a sourced report or draft.

## Read Order

1. Root `AGENTS.md`.
2. `personal/AGENTS.md` when present.
3. Relevant personal state:
   - `personal/goals/`
   - `personal/tasks/`
   - `personal/sideprojects/<slug>/AGENTS.md`
   - project `scope.md`, story, decisions, or log when needed
4. Named workspace router and project scope when reporting team/company work.
5. `context/log/`, personal log, workspace log, or project log entries only for
   recent history.
6. Nearest feedback index only when reporting feedback or improvement state.
7. Report references in this skill when shaping designer status or 1:1 output.
8. `context/knowledge/work-os/context-protocol.md` for structure/tooling
   questions.

If expected folders are missing, say they are not populated yet.

## Report Modes

- **status** - current state and next action.
- **weekly** - progress, blockers, shipped/applied outcomes, next week.
- **standup** - yesterday/today/blockers or equivalent concise team update.
- **1:1** - manager-facing topics, decisions needed, support requests, wins,
  risks.
- **goal** - progress against success signals and active projects/tasks.
- **project/workspace** - current state, decisions, questions, risks, next.
- **tooling/access** - access state, blockers, owner, next action; no secrets.
- **slack** - copy-pasteable team update.
- **email** - subject plus concise body.
- **doc** - local markdown/doc-ready structure.
- **mcp** - target-ready draft content; draft only unless publishing is explicit.

## Boundaries

- Lead with the current state and next action.
- Keep summaries short, sourced, and audience-aware.
- Separate confirmed facts from inferred status.
- Never expose secrets, tokens, cookies, `.env`, private config, or credentials.
- Never auto-publish to Slack, email, Confluence, Jira, or MCP destinations
  unless the user explicitly asks and the tool flow supports it.
- Do not create feedback entries; use `work-os-feedback` for that.
- Do not route system changes or graduation; use `work-os-reflect` for that.

## Maintenance

If a relevant `AGENTS.md`, `memory.md`, or feedback index exceeds 4,500
characters, mention it as a report risk. Do not perform extraction.
