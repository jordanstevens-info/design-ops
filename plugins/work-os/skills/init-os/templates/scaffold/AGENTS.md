# Work OS

Agent-routed work context. In solo mode, `personal/` is tracked local state.

## Load Order

1. Read this router first.
2. Read `personal/AGENTS.md` when user-specific state matters.
3. Read only files needed for the task.

Narrower routers override broader routers. Team/company/client work areas live
in `workspaces/`; personal projects live in `personal/sideprojects/`.

## Root Surfaces

- `context/` - shared Work OS context, knowledge, feedback, plans, logs,
  references, resources, and templates.
- `workspaces/` - team, company, client, or durable work areas.
- `drop-zone/` - raw intake awaiting routing.
- `sandbox/` - messy drafts, experiments, and unrouted thinking.
- `personal/` - solo-mode goals, tasks, voice, references, and side projects.
- `.agents/skills/` - local Work OS skills.
- `.claude/skills/` - mirrored skill copies for Claude.
- `.archive/` - historical imports and frozen prior versions.

- `context/knowledge/README.md` - bucket index.
- `context/knowledge/work-os/context-protocol.md` - context model.
- `context/knowledge/work-os/operating-principles.md` - quality and security doctrine.
- `context/knowledge/work-os/graduation-patterns.md` - promotion rules.

## Personal Layer

`personal/` may contain profile, goals, tasks, feedback, voice, references,
logs, and `sideprojects/`.

Do not store secrets, tokens, cookies, private config, `.env`, or credentials in
Work OS, tracked or personal.

## Size And Extraction

Keep every `AGENTS.md` and `memory.md` under 4,500 characters. Extract rules
to `context/knowledge/` or earned `standards.md`, corrections to
`context/feedback/`, and repeated behavior to a skill.

## Routing Rules

- Start flat. Add folders only when the work earns them.
- Do not create empty directories for future use.
- `AGENTS.md` routes; it is not the knowledge base.
- When work depends on tools, MCPs, repo ownership, org boundaries, source
  destinations, or external systems, and `context/knowledge/tooling-profiles.md`
  or `context/knowledge/orgs/*.md` exist, use `rg` to find the relevant sections
  before acting. Do not rely on the first chunk of a long profile. If those
  profiles do not exist yet, say so and route the fact to a follow-up rather than
  acting on an assumed source.
- `context/log/` is a receipt layer; canonical truth lives in routers, scopes,
  tasks, goals, decisions, and knowledge.
- When applying Work OS routing, skill, knowledge, scope, or task-state
  changes, create or update the nearest relevant `context/log/`, personal log,
  workspace log, or project log receipt unless the edit is typo-only or
  explicitly temporary.
- References inform work; resources are consumed by it. Neither is endorsed
  knowledge until promoted.
- Use `ideas.md` for lightweight ideas that may be worth revisiting but are
  not yet tasks, feedback, plans, or durable knowledge.
- Route feedback by subject, not source: agent/system feedback to
  `context/feedback/`, personal growth or review feedback to
  `personal/feedback/`, raw HR/review source material to
  `personal/references/hr/`, and project feedback to the nearest project scope
  before creating project `feedback/`.
- Read the nearest feedback index only when feedback matters; do not scan every
  entry.
- Use `work-os-feedback` and the nearest feedback template when drafting,
  routing, synthesizing, or updating feedback.
- Add rules directly to `AGENTS.md` only when short, strict, and needed before
  action. Route bulky rules to scoped standards or knowledge.
- Use `.context/` for generic branch context. Keep `.design/` only where an
  existing workflow requires it.
- Do not rewrite archived material.
- Treat `.archive/` as registered historical material; do not flag it as
  unregistered work.
- Treat `drop-zone/` and `sandbox/` as registered temporary surfaces. Only flag
  stale, promotable, sensitive, ambiguous, or repeatedly used items.
- Preserve repository dirty state unless explicitly asked to clean it.
- Do not auto-route unregistered work. Flag it and ask how to route it.

## Local Skills

- `work-os-prime` - read-only orientation.
- `work-os-feedback` - feedback intake, routing, and synthesis.
- `work-os-report` - reports and communication drafts.
- `work-os-reflect` - self-improvement, maintenance, and graduation.
- `work-os-audit` - read-only structural and routing checks.

Every `AGENTS.md` scope needs sibling `CLAUDE.md`: `@AGENTS.md` plus
Claude-only notes. Keep `.agents/skills/` and `.claude/skills/` in sync with
`diff -qr .agents/skills .claude/skills`.
