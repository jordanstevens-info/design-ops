---
name: work-os-feedback
description: >
  Use when the user wants to capture, classify, route, synthesize, update, merge,
  drop, or apply feedback from managers, peers, 360 reviews, stakeholders,
  projects, self-review, agents, subagents, or evals.
---

# Work OS Feedback

Primitive skill for feedback intake and routing. Process the signal, place it
near the subject it is about, and propose action only when the feedback earns
it.

## Read Order

1. Root `AGENTS.md`.
2. `personal/AGENTS.md` when personal growth or received feedback matters.
3. Nearest feedback index; use `context/feedback/README.md` for root Work OS,
   agent, system, or eval feedback.
4. Relevant goals, tasks, project `scope.md`, decisions, references, or logs.
5. `context/templates/feedback.md`,
   `context/templates/received-feedback.md`, or
   `context/templates/project-feedback.md` when drafting a feedback entry.
6. `context/knowledge/work-os/graduation-patterns.md` when promotion is unclear.

If a routed folder is missing, say it is not populated yet. Do not create new
folders unless the user explicitly asks to save, capture, apply, or update.

## Feedback Routing

Route by subject, not source:

- agent, system, eval, or Work OS behavior -> `context/feedback/`
- personal growth, manager, peer, 360, or performance feedback ->
  `personal/feedback/`
- raw review source material -> `personal/references/hr/`
- project or stakeholder feedback -> nearest project `scope.md`; create
  project `feedback/` only when repeated or multi-entry feedback earns it
- workspace/team feedback -> nearest workspace `feedback/` or scope

Source gives context and credibility. Subject decides where the feedback lives.

## Feedback Loop

1. Identify source: user, manager, peer, 360, stakeholder, self, agent,
   subagent, eval, or other.
2. Identify subject: personal growth, project, workspace/team, agent/system, or
   Work OS.
3. Decide outcome: drop, capture, synthesize, route, apply, merge, or update.
4. Choose template:
   - `context/templates/feedback.md` for system, agent, eval, or Work OS
     feedback.
   - `context/templates/received-feedback.md` for manager, peer, 360, or
     review-cycle feedback.
   - `context/templates/project-feedback.md` for stakeholder or project
     feedback.
5. Propose the route and next action before writing unless the user explicitly
   asked to save, capture, apply, update, or write.
6. If action is earned, route to the nearest task, goal, project scope,
   standard, knowledge, template, skill, plugin, or log receipt.

If the feedback is about structural Work OS health, rule compliance, missing
files, skill sync, or version drift, use `work-os-audit` to gather read-only
evidence before proposing broad changes. Feedback owns the signal; audit owns
the inspection.

## Action Bar

- One-off and unclear -> keep as captured feedback or drop.
- Repeated or high-signal -> synthesize into a theme.
- Concrete next step -> propose a task.
- Strategic growth signal -> propose a goal or career-vision update.
- Project impact -> update project `scope.md`, decision, or feedback entry.
- Repeated agent behavior -> route to `context/feedback/`, `AGENTS.md`,
  `context/knowledge/`, or a skill.

Do not turn every feedback item into a task. Feedback is an evidence and
interpretation layer; tasks, goals, and scope updates are downstream outcomes.

## Lifecycle

Status values:

- `captured` - saved as evidence, no action yet.
- `proposed` - a route or action is suggested, not accepted yet.
- `active` - load-bearing guidance or theme agents should notice.
- `applied` - a change was made because of the feedback.
- `graduated` - another artifact now owns the behavior or truth.
- `archived` - kept for history, no longer active guidance.
- `dropped` - intentionally not useful enough to keep active.
- `superseded` - replaced by newer feedback, synthesis, or doctrine.

Applied is not the end state. Feedback stays active while it changes future
behavior. It graduates when another artifact owns that behavior. It archives
only when it is no longer load-bearing.

Index placement:

- Active guidance/themes can include `active` or still-load-bearing `applied`.
- Pending sections are for `captured` or `proposed`.
- Recently applied is temporary visibility, not an archive.
- Graduated or historical sections mean canonical behavior now lives elsewhere.

For "latest feedback" queries, search the nearest relevant feedback homes and
distinguish feedback entries from `README.md` indexes. Unless the user asks for
indexes, report the latest actual feedback entry with scope, status, route, and
modified time when available.

## Boundaries

- Proposal-first by default.
- Never store secrets, tokens, cookies, `.env`, credentials, or private config.
- Do not copy raw sensitive HR detail into tracked files unless it belongs in
  tracked personal context and the user explicitly asks.
- Do not auto-route unregistered work; use `work-os-reflect` for broader
  maintenance and graduation passes.
- Do not use feedback as a substitute structural audit. Hand off to
  `work-os-audit` when the user is asking whether Work OS follows its rules.
- Do not scan every feedback entry by default; start from the nearest feedback
  index.

## Output

For planning or intake, keep output compact:

```text
1. <feedback signal>
   Subject: <personal | project | workspace | agent/system | Work OS>
   Route: <path or drop>
   Action: <capture | synthesize | task | goal | scope | knowledge | skill | drop>
   Reason: <why>
```

When writing an entry, include a short `Applied Outcome` only after the route or
behavior actually changed.
