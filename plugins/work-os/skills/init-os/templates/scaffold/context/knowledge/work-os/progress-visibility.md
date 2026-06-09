# Progress Visibility

Progress visibility is Work OS doctrine. Its job is to make meaningful movement
visible without turning work into a game.

## Principles

- Make progress visible, not performative.
- Reward meaningful movement over task volume.
- Pair work left to do with work accomplished in the same period.
- Keep adoption opt-in if this later becomes a plugin upgrade.
- Avoid badges, points, levels, streaks, praise copy, kudos, fake scores, and
  competitive framing.

## Progress Signals

Use explicit denominators when they exist: weekly focus sets, success signals,
task sets, or project milestones. Show `n/m`, percentages, or `[======----]`
bars only when the denominator is clear. If the denominator is inferred, label
it as inferred or avoid a numeric score.

Use bars intentionally, not as decoration. Default to one primary bar for the
weekly focus or requested focus set. Use secondary bars only when the user asks
for comparison or each row has the same kind of explicit denominator. Use
`n/m`, quiet bands, or short text for goal coverage and WIP pressure.

Count movement from shipped outcomes, applied decisions, task movement, blocker
reduction, clarified scope, useful artifacts, or goal coverage. Newly started
work may be visible, but it is not progress by itself. Do not inflate progress
from file churn alone.

## Display Pattern

Start with the current focus state, then show movement before remaining work:

```text
Weekly focus: [======----] 6/10 complete

Moved This Week
Done
- <completed or applied item>

Moved
- <advanced, unblocked, or clarified item>

Still In Focus
Next
- <remaining focus item>; finish by <finishable move>
```

Use quiet bands such as `on track`, `needs attention`, and `underinvested`.
Show WIP pressure when active tracks exceed the useful focus limit. End with
the nearest valuable finish move.

## Surface Responsibilities

- `work-os-report` renders structured progress snapshots and communication
  formats.
- `work-os-prime` uses recent movement, remaining focus, and meeting-aware
  timing to choose the next useful focus without becoming a report.
- `work-os-reflect` checks whether Work OS made movement and remaining focus
  visible, then routes durable fixes to knowledge, templates, or skills.
- A plugin upgrade can later make this opt-in across installed Work OS
  instances; the local task model should not change just to support display.
