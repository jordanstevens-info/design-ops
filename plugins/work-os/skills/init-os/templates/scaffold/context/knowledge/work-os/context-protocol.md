# Context Protocol

Canonical Work OS context doctrine. `AGENTS.md` routes agents here
when they need the operating model behind routers, knowledge, feedback,
templates, skills, and scoped context.

## Thesis

Work OS is fractal by behavior, not by identical folders.

```text
AGENTS.md routes the agent
context/knowledge gives durable shared context
context/feedback routes root actionable signals by subject
ideas park optional possibilities for later
context/templates shape shared repeated artifacts
skills turn repeated behavior into reusable workflows
```

The files differ by scope. The jobs stay consistent. Agents start with
`AGENTS.md`, because it is automatically available at the relevant filesystem
scope, then follow the read order there and load only what changes the work.

## Primitives

- **Router** - `AGENTS.md` at the current scope. It defines scope, read order,
  source routing, invariants, and what not to do.
- **Knowledge** - durable truth for future work. Shape varies by scope.
- **Feedback** - actionable signals that should improve future behavior,
  personal growth, or project outcomes. Feedback is high-signal and routed by
  subject; it is not transcript storage.
- **Ideas** - lightweight possibilities worth revisiting. Ideas are not tasks,
  feedback, plans, or commitments. Capture them cheaply and promote them only
  when they earn action.
- **Templates** - reusable artifact shapes that should be easy to tweak
  without editing skill logic.
- **Skills** - executable workflows. Primitive skills do one thing; workflow
  skills chain primitives; orchestrators coordinate workflows or subagents.
- **References** - source material and prior art that informs work. References
  are not endorsed until promoted.
- **Resources** - reusable working inputs consumed by local work, such as
  design-system kits, asset packs, fixtures, prototype dependencies, and
  reusable example apps.
- **Artifacts** - outputs worth keeping. Useful, but not part of the core
  context contract.
- **Drop Zone** - raw incoming material awaiting routing.
- **Sandbox** - messy exploratory work, drafts, and unrouted thinking. Avoid
  `tmp/`, `temp/`, and vague scratch folders.

Do not create every primitive at every level. A scope gets only the pieces it
uses.

## Context Unit

Each level can be understood as a context unit:

```text
<context>/
  AGENTS.md              # injected router: read order, invariants, scope rules
  README.md              # optional human/package index when useful
  knowledge.md           # or knowledge/ when it earns multiple files
  ideas.md               # optional parked ideas worth revisiting
  feedback/              # proposed or active corrections that may graduate
  templates/             # optional reusable artifact shapes
  resources/             # optional reusable inputs consumed by the work
  artifacts/             # optional outputs worth keeping
  .agents/
    skills/              # optional local repeatable workflows
```

No knowledge filenames are mandatory. Use names that match the scope:

- `vision.md` when direction matters.
- `architecture.md` when shape and relationships matter.
- `standards.md` when repeated rules matter.
- `ideas.md` when possibilities need to be parked without becoming tasks.
- `working-agreements.md` when team behavior matters.
- `sources.md` or `tooling.md` when external systems matter.
- `design-system.md` when tokens, components, or patterns matter.
- `state.md` or `work.md` when current operating reality needs its own file.

The invariant is the job, not the filename.

## Scope Mapping

```text
root/
  AGENTS.md              # shareable Work OS router and invariants
  drop-zone/             # raw incoming material awaiting routing
  sandbox/               # exploratory rough work and unrouted thinking
  personal/              # tracked solo-mode layer
  workspaces/            # team/company/client areas
  context/
    knowledge/           # reusable cross-scope truth
    feedback/            # OS-level agent/eval/Work OS corrections
    templates/           # shared non-skill templates
    references/          # public source material and prior art
    resources/           # shared reusable inputs consumed by local work
    plans/               # shared planning drafts and approved plans
    log/                 # dated receipts for shareable Work OS changes
  .agents/skills/        # prime, feedback, report, reflect, future OS workflows

personal/                # tracked solo-mode personal layer; can be ignored for team distribution
  AGENTS.md              # local user router and overrides
  profile.md             # user settings when needed
  ideas.md               # optional personal ideas
  goals/
  tasks/
  feedback/              # received feedback and growth themes
  voice/
  references/            # raw personal source material, including HR docs
  resources/             # optional personal reusable inputs
  log/

workspaces/<area>/
  AGENTS.md              # team/company/client area router and overrides
  ideas.md               # optional area ideas not yet projects
  knowledge.md           # or knowledge/ for area-durable context
  feedback/              # area feedback, retros, recurring patterns
  log/
  templates/             # only when area-specific templates are earned
  references/            # source material and prior art when earned
  resources/             # reusable area inputs consumed by local work

workspaces/<area>/projects/<slug>/
  AGENTS.md              # optional project router when context is deep
  ideas.md               # optional project ideas before they become scope
  scope.md               # working brief/control file
  knowledge.md           # or knowledge/ if the project needs depth
  feedback/              # earned project feedback and validation takeaways
  log/
  references/            # project source material when earned
  resources/             # project-local kits, assets, fixtures, dependencies
  artifacts/

personal/sideprojects/<slug>/
  AGENTS.md              # personal project router when needed
  ideas.md               # optional side-project ideas before they become scope
  scope.md               # working brief/control file
  knowledge.md           # or knowledge/ if the side project needs depth
  feedback/
  log/
  references/
  resources/
  artifacts/

repositories/<repo>/
  README.md              # repo index or existing project README
  AGENTS.md              # implementation context
  knowledge/             # if the repo owns durable implementation knowledge

repositories/<repo>/.context/
  AGENTS.md              # branch/session router if agents work inside context
  README.md              # optional, or required when a workflow expects it
  ideas.md               # optional branch/session ideas
  knowledge.md           # or knowledge/ for branch-specific context
  feedback/              # or log/ for dated branch progress
  resources/             # branch/session inputs consumed by prototypes or tools
  artifacts/
  drop-zone/             # raw incoming material, only when needed
  sandbox/               # exploratory branch/session work, only when needed
```

Use `.context/` for generic branch context. Keep `.design/` only where an
existing design-engineering workflow explicitly requires that name.

## Minimum Viable Work OS

The minimum shareable Work OS is root `AGENTS.md`, `context/knowledge/`,
`context/feedback/`, `context/templates/`, `context/log/`, and local skills.
The minimum private installation adds `personal/AGENTS.md`, then
`personal/goals/`, `personal/tasks/`, or `personal/sideprojects/` only when
populated. Team/company/client work uses top-level `workspaces/`.

Ideas, references, resources, drop-zone, sandbox, story, decisions, research,
and deeper project folders are optional until the work earns them.

## Workspace Threshold

Default to no new workspace for a single idea. A workspace is earned by
repeated future work, multiple projects, durable stakeholders, or area
knowledge that needs a home. Until then, start inside an existing workspace,
project, task, or sandbox note and promote only when the work proves it will
recur.

## Idea Capture

Ideas are the parking layer for possibilities that may be useful later but do
not yet deserve task, feedback, plan, or project weight.

Capture ideas in the nearest useful `ideas.md`:

- root `ideas.md` for cross-scope Work OS or operating-model ideas
- `personal/ideas.md` for personal or career ideas
- `workspaces/<area>/ideas.md` for area ideas not yet tied to one project
- project `ideas.md` for ideas attached to an active project
- `.context/ideas.md` or `.design/ideas.md` only for branch-scoped ideas

An idea entry should be dated, titled, and light. It can include why it might
matter, where it applies, rough impact/effort/confidence, a possible next move,
and a status such as `parked`, `explore`, `promote`, or `drop`.

Ideas promote when they earn weight:

```text
idea
-> scope.md when it becomes project direction
-> context/plans/ when it needs shared structured thinking
-> tasks/ when it needs action
-> context/feedback/ when it is actually a root correction signal
-> context/knowledge/ when it becomes durable shared truth
-> context/templates/ or skills when the shape or behavior repeats
```

Do not turn ordinary idea capture into a backlog. The default status is
`parked`; review or promote only when the user asks, the idea recurs, or it
becomes relevant to active work.

## Knowledge Examples By Scale

| Scale | Router examples | Knowledge examples | Feedback examples | Skill examples |
| --- | --- | --- | --- | --- |
| Personal | How I work, what to load, what not to touch | Personal goals, career vision, preferences, active work map, trusted tools | Received feedback, growth themes, recurring friction, useful defaults | Prime my day, feedback intake, weekly report, reflect, route scattered notes |
| Team | Working agreements, rituals, handoff rules, team source routing | Team priorities, stakeholders, design standards, review norms, shared tools | Retro outcomes, recurring blockers, decision patterns, onboarding gaps | Standup update, design review prep, research synthesis, handoff package |
| Company | Company constraints, source-of-truth routing, access boundaries | Product map, tooling profiles, account/access notes, policies, design-system maturity | Company-wide operating patterns, repeated tool issues, cross-team handoff feedback | Ticket creation, MR package, onboarding brief, quarterly report synthesis |
| Org / multi-company | Tenant/client boundaries, confidentiality, per-company routing | Federated source maps, shared protocols, company exceptions, escalation paths | Patterns to propagate, risks that repeat across companies | Cross-company research watch, portfolio review, multi-agent orchestration |

## Agent Read Order

At any scope:

```text
AGENTS.md
-> personal/AGENTS.md when present and user-specific state matters
-> README.md only if AGENTS.md or a workflow points there
-> knowledge.md or specific knowledge files named by AGENTS.md
-> ideas.md only when capturing, revisiting, or promoting ideas
-> nearest feedback/README.md only when feedback context matters
-> log only when recent history matters
-> templates only when creating or validating an artifact
-> resources only when the work consumes local kits, assets, fixtures, or deps
-> artifacts only when the task points there
```

`AGENTS.md` must say what knowledge exists, which external sources matter,
whether README or ideas should be read, and which skills should be used for
repeated workflows. Do not bulk-load a workspace because it exists.

## Template Layer

Templates are reusable artifact shapes: `scope.md`, idea entries, feedback
entries, decision entries, log entries, status updates, handoff packages,
ticket bodies, MR descriptions, research plans, and presentation outlines.

Put a template where its reuse lives:

- A template used by one skill can live inside that skill folder.
- A template used by many local skills can live in `.agents/templates/` at the
  relevant context.
- A shared template not owned by skills can live in `context/templates/` and be
  routed by `AGENTS.md`.
- A template required by a distributed skill or plugin must ship with the
  skill or plugin.
- `.agents/skills/` contains behavior: when to use a template, how to fill it,
  what to validate, and where to save the result.

Template resolution order:

```text
explicit path from user or AGENTS.md
-> local templates/
-> .agents/templates/
-> skill-local templates/
-> plugin-bundled templates/
```

## Skill Layers

Skills live beside the context they operate on.

```text
.agents/skills/
  primitives/
    inspect-context/
    summarize-source/
    update-state/
    work-os-feedback/
    route-unregistered/

  workflows/
    prime/
    report/
    reflect/
    design-engineer/
    create-ticket/
    create-mr/

  orchestrators/
    weekly-review/
    cross-project-sweep/
    handoff-package/
    cloud-research-watch/
```

The rule is composition:

```text
primitive skills
-> workflow skills
-> orchestrator skills
```

Primitive skills should be tiny and reusable. Workflow skills should chain
primitives for one outcome. Orchestrators are justified only when they
coordinate multiple workflows, contexts, tools, or subagents.

Local skill folders may remain flat when the loader expects
`.agents/skills/<name>/`. A flat folder can still be documented as a primitive.

## Feedback To Skill Loop

Feedback matters only if it changes future behavior, growth direction, or
project outcomes. Route by subject, not source:

- agent, eval, system, or Work OS behavior -> `context/feedback/`
- personal growth, manager, peer, 360, or performance feedback ->
  `personal/feedback/`
- raw review source material -> `personal/references/hr/`
- project or stakeholder feedback -> nearest project `scope.md`; create project
  `feedback/` only when repeated or multi-entry feedback earns it
- workspace/team feedback -> nearest workspace `feedback/` or scope

```text
feedback signal
-> classified by `work-os-feedback`
-> feedback captured near its subject, in a log, or drafted template
-> indexed in the nearest feedback README when agents should notice it
-> promoted into knowledge when durable
-> routed from AGENTS.md when agents need it
-> operationalized as a primitive skill when repeated
-> chained into a workflow skill when the primitive set stabilizes
-> promoted to orchestrator only when coordinating multiple workflows/subagents
```

Use `context/templates/feedback.md`,
`context/templates/received-feedback.md`, or
`context/templates/project-feedback.md` when drafting root/shared feedback.
Route to the nearest appropriate scope first. Promote upward only when the
feedback is cross-scope, repeated, load-bearing, or team-facing. Agents read
the nearest feedback index first; they do not scan every feedback entry by
default.

Feedback stays active while it changes future behavior, growth direction, or
project outcomes. `applied` means a change happened; it does not mean the entry
should be archived. Feedback graduates when another artifact owns the behavior
and archives only when it is no longer load-bearing.

## Tooling Profiles

Tooling profiles are cross-cutting knowledge, not saved machine config.

They can describe team defaults, account aliases, Git hosts, Atlassian spaces,
VPN needs, MCP/tool surfaces, product links, design systems, and exceptions.
They must not contain passwords, tokens, API keys, cookies, private
`.mcp.json`, `.env`, or machine-specific secrets.

If `context/knowledge/tooling-profiles.md` or
`context/knowledge/team-map.md` has not been created yet, agents should say
the files are not populated yet and route the fact through a follow-up plan,
a project `scope.md` tooling override, or a proposed profile/map update.

## Profile Routing

A profile is a role or context pack, not a required folder. Use profiles to
describe reusable defaults for a user, org, team, client, or tool context.

Default storage:

- `personal/profile.md` for user settings, preferences, voice, and personal
  defaults.
- `context/knowledge/tooling-profiles.md` for cross-cutting tooling defaults,
  account aliases, access context, and exceptions.
- `context/knowledge/orgs/<org>.md` when one org, team, or client needs source
  maps, working agreements, destination rules, product maps, or knowledge
  pointers.
- `workspaces/<area>/AGENTS.md` and project `scope.md` for active-work
  overrides and exceptions.

Profiles provide defaults. Scope owns reality. If a workspace or project
contradicts a profile, trust the narrower router or scope and route the
exception back into the profile only when it repeats or changes future work.

Do not create a top-level `profiles/` directory for current Work OS by default.
That folder is earned only when profile packs need lifecycle operations such as
install, enable, update, remove, audit, versioning, or cross-repo sync.

## Guardrails

- The pattern is consistent; the files are earned.
- `AGENTS.md` routes; it does not become the whole knowledge base.
- Every `AGENTS.md` scope needs a sibling `CLAUDE.md` adapter containing
  `@AGENTS.md` plus Claude-only notes.
- Keep `AGENTS.md` and `memory.md` under 4,500 characters; extract overflow to
  `context/knowledge/`, `context/feedback/`, standards, or skills.
- `README.md` exists only when it serves humans, distribution, or an explicit
  workflow.
- Knowledge file names are local choices, not required categories.
- Feedback is high-signal and actionable, not transcript storage.
- Ideas are optional possibilities, not obligations.
- Skills operationalize repeated feedback; they do not exist for tidiness.
- Branch context uses `.context/` unless the workflow is explicitly design-only
  and still relies on `.design/`.
- Local skills start as primitive, reusable actions before becoming workflows.
- Meta-skills and orchestrators are allowed only when they coordinate multiple
  workflows or subagents.
- Promotion requires evidence of reuse, durability, or future value.
