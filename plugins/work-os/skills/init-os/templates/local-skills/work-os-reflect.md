---
name: work-os-reflect
description: >
  Use when the user asks to reflect, close a session, self-improve Work OS,
  route unregistered work, or graduate repeated feedback into durable Work OS
  material.
---

# Work OS Reflect

Session self-improvement and graduation. Filter what happened, use
`work-os-feedback` for actual feedback signals, and propose only the Work OS
changes that earned action.

## Read Order

1. Root `AGENTS.md`.
2. `personal/AGENTS.md` when present.
3. `context/feedback/README.md` only when system feedback changes the
   reflection.
4. `personal/feedback/README.md` when personal feedback changes the reflection.
5. Relevant personal goals, tasks, project scopes, decisions, and logs.
6. `context/knowledge/work-os/graduation-patterns.md` when routing is unclear.
7. Recent `Applied Outcome` sections to avoid repeated proposals.

If a routed folder is missing, say it is not populated yet.

## Reflection Loop

1. Identify whether the session contains real feedback. If yes, use
   `work-os-feedback` rules to classify the signal before proposing a route.
2. Identify whether the session requires structural evidence. If the user asks
   whether Work OS is healthy, messy, compliant, stale, synced, version-current,
   or missing expected files, use `work-os-audit` before proposing changes.
3. Propose routed updates only when the signal earned action:
   - receipt -> nearest relevant `context/log/`, personal log, workspace log,
     or project log
   - surfaced task -> `personal/tasks/not_started/`
   - active/blocked/done task -> move within `personal/tasks/`
   - project status -> project `scope.md`
   - short strict rule -> `AGENTS.md`
   - bulky or repeated judgment -> standards or `context/knowledge/`
   - durable truth -> `context/knowledge/`
   - repeated artifact shape -> `context/templates/`
   - repeatable behavior -> local skill
4. Propose maintenance:
   - remove empty live directories;
   - add missing `CLAUDE.md` adapters beside `AGENTS.md` routers;
   - extract any `AGENTS.md`, `memory.md`, or feedback index over 4,500
     characters;
   - route stale `context/plans/`, `drop-zone/`, `sandbox/`,
     `context/references/`, and `context/resources/` as keep active, promote,
     convert, archive, or drop;
   - treat `drop-zone/` and `sandbox/` as buckets by default; name individual
     files only when stale, promotable, sensitive, ambiguous, repeatedly used,
     or user-requested;
   - flag unregistered work and ask how to route it.

## Log Receipts

Use `context/templates/log.md` when creating a new log. Logs must add context
beyond the commit message: why the change mattered, decisions made, tradeoffs,
applied outcomes, evidence, or follow-ups. Do not create logs that only restate
file changes.

## Feedback To Rules

Add a rule directly to `AGENTS.md` only when it is short, strict, and needed
before an agent acts. Route bulky rules to scoped standards or knowledge.

Use existing Work OS knowledge first: operating principles, context protocol,
and graduation patterns in `context/knowledge/`. Create `standards.md` only
when clearly earned.

For feedback intake, capture, synthesis, status updates, merge/drop decisions,
or direct user feedback manipulation, use `work-os-feedback`. Reflect only
decides whether a session or repeated signal should change Work OS.

For structural health checks, use `work-os-audit`. Reflect consumes audit
findings and proposes or applies approved changes; it does not need to perform
the full audit itself.

## Boundaries

- Proposal-first. Write only when explicitly asked to save, apply, capture,
  update, write, or commit.
- Do not store secrets, tokens, cookies, `.env`, private config, or credentials.
- Do not treat `context/log/` as canonical truth. Update routers, scopes,
  tasks, decisions, feedback, or knowledge when they carry real state.
- Do not auto-route unregistered work.
- `Nothing worth reflecting` is valid.

## Output

Keep the reflection short and numbered:

```text
1. <self-improvement, graduation, or routing item>
   Route: <log | task | scope | feedback | AGENTS | standard | knowledge | template | skill | drop>
   Reason: <why it belongs there>

2. <maintenance item>
   Route: <keep | promote | convert | archive | drop>
   Reason: <why this is the next action>
```

When the user approves numbered items, apply only those items. For applied Work
OS routing, skill, knowledge, scope, or task-state changes, create or update the
nearest relevant `context/log/`, personal log, workspace log, or project log
receipt unless the edit is typo-only or explicitly temporary. When feedback is
written, keep the nearest feedback index and `Applied Outcome` current.
