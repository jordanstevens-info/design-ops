# Graduation Patterns

## Principle

Don't ask "where should this go?" first. Ask whether the work has earned more
structure.

Something graduates when it becomes reused, active, load-bearing, or
team-facing. Five complementary paths: idea graduation, project-artifact
graduation, knowledge graduation, template graduation, and tooling graduation.

## Idea path

Ideas are lightweight possibilities worth revisiting. They are not tasks,
feedback, plans, or commitments.

```text
idea entry in nearest ideas.md
-> scope.md when it becomes project direction
-> context/plans/ when it needs shared structured thinking
-> tasks/ when it needs action
-> context/feedback/ when it is actually a root correction signal
-> context/knowledge/ when it becomes durable shared truth
-> context/templates/ or skills when the shape or behavior repeats
```

Use the nearest useful `ideas.md`: root for cross-scope ideas,
`personal/ideas.md` for personal ideas, workspace `ideas.md` for area ideas,
project `ideas.md` for project-specific possibilities, and `.context/ideas.md`
or `.design/ideas.md` for branch-scoped ideas. Do not create an idea folder
until one file needs supporting material, multiple outputs, repeated sessions,
or a log of its own.

Default status is `parked`. Promote only when the user asks, the idea recurs,
or it becomes relevant to active work. Drop ideas freely when they no longer
carry useful possibility.

## Project artifact path

Inside a project folder, artifacts grow organically:

```text
ideas.md (rough notes)
-> scope.md sections (problem, current state, questions)
-> research/ (when first user contact happens)
-> wireframes/ (when first wireframe lands)
-> decisions.md (when first decision is made)
-> prototypes/ (when first prototype runs)
-> story.md sections (as the snowball thickens)
-> presos/<topic>/ (when a presentation is needed)
```

Not every project needs every step. The minimum-viable active project is
`scope.md`. Add `story.md` when narrative, handoff, or presentation work
begins.

## Knowledge path

Knowledge graduates vertically through the hierarchy:

```text
project note (in scope.md, ideas.md, or research/)
-> workspace knowledge (when pattern recurs across one project's iterations)
-> context knowledge (when pattern recurs across workspaces)
-> Confluence (when team-facing)
```

Each step requires evidence the pattern is durable, not a one-off detail.

## Profile path

Profiles are reusable defaults for a user, org, team, client, or tool context.
They graduate from concrete work, not from abstract taxonomy.

```text
project or workspace tooling/source exception
-> project scope.md or workspace AGENTS.md override
-> context/knowledge/tooling-profiles.md when it repeats across work
-> context/knowledge/orgs/<org>.md when the context spans tools, sources, defaults,
   working agreements, destinations, or knowledge pointers
-> profile pack or plugin when it should install into another Work OS
-> profiles/ only when lifecycle operations require a dedicated layer
```

Use `personal/profile.md` for user-specific preferences and defaults. Keep
org/team/client profiles out of `personal/` unless they are private notes about
the user's own relationship to that context.

Profiles provide defaults. Scopes own reality. Narrower workspace routers and
project scopes override profile defaults; repeated exceptions can graduate back
into the profile.

## Tooling path

Use this path for repeatable agent behavior:

```text
feedback signal
-> feedback index / standard / AGENTS.md / context/knowledge/
-> project skill
-> user-level skill
-> plugin
```

When answering where feedback should go, include the draft step: use
`work-os-feedback` and the nearest feedback template when drafting the feedback
proposal. Route by subject, not source: OS-level feedback goes to
`context/feedback/`, personal growth feedback goes to `personal/feedback/`,
raw HR source material goes to `personal/references/hr/`, and project feedback
starts in the nearest project `scope.md`. Promote upward only when the feedback
is repeated, cross-workspace, load-bearing, or team-facing.

Feedback lifecycle:

```text
captured -> proposed -> active -> applied -> graduated -> archived
exit states: dropped, superseded
```

Applied is not the end state. Feedback stays active while it changes future
behavior. It graduates when another artifact owns that behavior. It archives
only when it is no longer load-bearing.

Decision rules:

- Do it once: capture the feedback only if future behavior should change.
- Do it twice: standardize it in `AGENTS.md` or `context/knowledge/`.
- If the agent needs to perform it end-to-end: make it a project skill.
- If it should work outside this Work OS: make it a user-level skill.
- If it should ship to a team or bundle skills, agents, commands, hooks, or
  MCP behavior: make it a plugin.
- If it changes how people collaborate: publish or update Confluence
  methodology.
- If it is generic branch context: keep it in `.context/` unless it becomes
  durable.
- If it is branch-scoped design engineering context for a workflow that
  explicitly requires `.design/`, keep it there unless it becomes durable.

Bootstrapping note: `work-os-feedback` is allowed before two manual repetitions
because its procedural shape is known and it exists to prevent inconsistent
feedback capture. `work-os-reflect` remains the workflow for self-improvement,
maintenance, and graduation proposals.

### Skill portability

When a skill graduates beyond a one-off, ship its references inside the
skill folder (`<skill>/references/`). Don't leave the skill depending on
user-specific files at root. The skill becomes portable across users,
harnesses, and future plugins; user-specific examples can still live
outside the skill as personal history.

## Template path

Use this path for repeatable artifact shapes:

```text
one-off artifact
-> copied shape
-> local template
-> shared skill template
-> plugin-bundled template
```

Decision rules:

- If only humans use it, keep shared templates in `context/templates/`.
- If several local skills use it, put it in `.agents/templates/`.
- If one skill owns it, put it inside that skill folder.
- If a distributed plugin requires it, ship it with the plugin or skill.
- If changing it would affect active workflows, note the change in log.

## Design system as you go

Components, patterns, or tokens invented for a project graduate from
`workspaces/<area>/projects/<slug>/` into the design-system workspace or repo
when reused or stable. This keeps the design system growing from real project
work instead of "design system later."

## File to folder

A single `.md` graduates to a folder when it needs:

- supporting files
- samples
- repeated sessions
- multiple outputs
- multiple audiences
- a log of its own

Don't graduate a file to a folder just because the folder would look tidy.

## Project to workspace

A standalone project under one workspace graduates to its own workspace when
it becomes a durable area of work with multiple sub-projects, its own
stakeholders, and its own knowledge.

Example:

```text
workspaces/<area>/projects/<slug>/
-> workspaces/<slug>/  (only if it grows into multiple projects or a full team-facing area)
```

Default is to grow within an existing workspace. New team/company workspaces
are expensive; personal projects belong in `personal/sideprojects/`.

## Project shipped/archived

Flip `status` in `scope.md` to `shipped` or `archived`. The project folder
stays in place inside the workspace as durable history. `story.md` becomes a
finished case study; pieces graduate into portfolio material as appropriate.

## Feedback And Reflect

Use `work-os-feedback` when the task is direct feedback intake,
classification, routing, synthesis, status updates, merge/drop decisions, or
application. It processes the signal and proposes where it belongs.

Run `work-os-reflect` after meaningful sessions, corrections, retros, or
end-of-day close. Its job is to filter the session for Work OS
self-improvement, graduation opportunities, log/task/scope/knowledge proposals,
and maintenance. It also reviews **unregistered work** introduced during the
session — folders or files not represented in `AGENTS.md`, `personal/AGENTS.md`,
`ideas.md`, `context/knowledge/`, `context/feedback/`, `personal/feedback/`,
`personal/goals/`, `personal/tasks/`, `context/templates/`, `context/plans/`,
or any project `scope.md` — and asks the user how to route each one rather
than auto-organizing.

The purpose is portability. Agent applications may keep private session
history, but that history is often trapped inside one harness. Work OS feedback
and reflect promote useful signals into files that travel across Claude, Codex,
plugins, future agents, and humans.

`Nothing worth reflecting` is a valid reflect result. Don't turn ordinary
execution details, speculative risks, or one-off nits into Work OS doctrine.

Both skills are proposal-first. They write only when explicitly asked to save,
apply, capture, update, write, or commit.

## Branch Context

Use `.context/` for generic branch-scoped context inside a repository. Use
`.design/` only for branch-scoped design engineering context when an existing
workflow requires that name. Promote durable patterns out of branch context
only when they would help future branches or teams.
