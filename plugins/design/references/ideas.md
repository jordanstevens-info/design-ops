# Ideas

Ideas are lightweight possibilities. They are not tasks, feedback, plans, scope,
or commitments until they earn promotion.

Use idea capture when the user says something like:

- "I have an idea"
- "save this for later"
- "jot this down"
- "what if we tried..."
- "let's explore options"
- "we may want to revisit this"

## Destination

Put ideas in the nearest useful place:

- `.design/ideas.md` for repo-backed or branch-scoped design ideas
- `.context/ideas.md` when the host repo uses generic branch context
- a project or workspace `ideas.md` when the host has that convention
- inline only when no durable destination exists or the user has not approved
  writing files

Do not create empty idea files. Create `ideas.md` only when there is a real idea
entry to save.

## Entry Shape

Use `../templates/ideas/idea-entry.md` for a full entry. Keep capture cheap:

- Date
- Title
- Source
- Status: `parked`, `explore`, `promote`, or `drop`
- Applies to
- Idea
- Why it might matter
- Possible next move

## Promotion

Promote only when the idea earns weight:

```text
idea
-> scope when it becomes direction
-> prototype when it needs options or interaction evidence
-> research packet when the assumption is the problem
-> validation plan when the artifact needs evidence
-> jira-update when it is delivery-ready
-> feedback report when it reveals a correction signal
-> knowledge or templates when it becomes durable or repeated
```

Default status is `parked`. Do not turn ordinary idea capture into a backlog.

## Evaluation

When comparing ideas or prototype options, evaluate against:

- user value
- business or workflow value
- evidence quality
- design-system fit
- accessibility and inclusion risk
- implementation confidence
- data handling constraints
- cost of being wrong

If the idea cannot be evaluated yet, capture the missing evidence instead of
forcing a decision.
