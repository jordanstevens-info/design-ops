# Operating Principles

Work OS should stay light, fast, and agentic. Large-scale problems do not need
large-scale local scaffolding; they need small, clear primitives inside a
large-scale framework.

## Quality First

The point isn't to make work look faster. The point is to raise the quality of
the output so everyone around the work moves faster.

Slop is cheap. Quality is hard. If anyone can produce the same thing, it has
no strategic value.

## Quality Bar — Anti-Slop

Every design decision must be defensible. Shooting from the hip is the
fastest path to slop.

- **Defensibility.** Each decision needs backing — data, research finding,
  best practice, or stakeholder validation. Multiple backings strengthen the
  call. Captured in the project's `decisions.md`.
- **Assumption discipline.** Surface assumptions through the open-questions
  section of `scope.md`. Each question is an assumption to test. When the
  assumption space is deep enough to need explicit risk-ranking, graduate to
  `assumptions.md`.
- **Decision log requirement.** Once a project has decisions, it has
  `decisions.md`. Forward-only. Reversed calls get new entries referencing
  the prior one — never edit history.
- **Validation discipline.** Success criteria are measured, not assumed.
  Baseline + post-launch measurements live in `research/` and roll back into
  scope's success criteria section.

If a decision can't be defended, it isn't ready. Either find the backing or
mark it explicitly as a gut call so it can be revisited.

## Knowledge Solidity Levels

Not all knowledge sits at the same level of certainty. Three solidity tiers,
filed by where they live:

- **Musings** (`workspaces/<area>/knowledge/musings/`) — concept-stage
  thinking. Speculative visions, half-formed ideas, "maybe-tasks." May firm
  up, may dissolve. Don't treat as load-bearing.
- **Workspace knowledge** (`workspaces/<area>/knowledge/`) — area-durable
  truth. Patterns and decisions that hold across projects in this workspace.
- **Context knowledge** (`context/knowledge/`) — cross-workspace truth.
  Patterns that hold across two or more workspaces.

Files graduate (or get deleted) as they prove out. Don't let musings linger
indefinitely — promote, transform into a project, or let go.

## Right Context At The Right Time

Agents should not hunt. `AGENTS.md` routes the scope, knowledge carries durable
truth, templates shape common artifacts, and skills execute repeatable work.

Good context is:

- **small** - short enough to fit in working context;
- **scoped** - specific to root, workspace, project, repo, or branch;
- **current** - tied to active goals, tasks, projects, or recent log;
- **actionable** - it changes what the agent should do next.

If a doc becomes a maze, split or demote it. If a pattern repeats, promote it.

## Human Judgment Stays Central

AI can generate options, synthesize material, draft artifacts, and accelerate
execution. The designer owns intent, judgment, taste, tradeoffs, and final
quality.

AI outputs do not graduate directly to stakeholders, teams, or implementation
without review.

## Scope, Story, Decisions

Project work runs through three load-bearing files:

- `scope.md` — working brief. Drives day-to-day. Stays current.
- `story.md` — narrative spine. Snowballs into the case study.
- `decisions.md` — append-only audit trail. Defends the work.

The working loop runs through all three: questions in scope drive research,
research informs decisions, decisions are narrated in story, success criteria
in scope validate the result.

## Constrain the Plumbing, Liberate the Paint

Use strict instructions where small mistakes break the work:

- file paths
- data contracts
- API routes
- workflow sequence
- security boundaries
- state management
- scope boundaries

Use lighter guidance where judgment improves the outcome:

- writing tone
- visual hierarchy
- interaction feel
- information grouping
- presentation narrative

## In-Repo vs Out-of-Repo

Use out-of-repo work for early thinking, methodology, research, and
team-facing drafts.

Use repo-backed work when implementation reality matters: components, tokens,
routes, build constraints, visual fidelity, accessibility, production handoff.

Use branch-scoped `.context/` when a repo branch needs portable context that
should not become permanent repo documentation. Keep `.design/` only where an
existing design-engineering workflow explicitly depends on that name.

## Tooling Is Context, Not Secrets

Work OS may describe which team tooling applies to a workspace or project:
account aliases, Git hosts, Jira or Confluence surfaces, MCP/tool names, VPN
needs, product links, and one-off exceptions.

Work OS must not store passwords, tokens, API keys, cookies, private
`.mcp.json`, `.env`, or machine-specific secrets.
