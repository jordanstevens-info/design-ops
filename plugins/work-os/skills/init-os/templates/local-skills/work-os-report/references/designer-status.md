# Designer Status Report — shape

Per-period (typically weekly) update covering active goals and projects in a
designer's portfolio. Used for async leadership updates, manager reviews, and
cross-team visibility.

## Shape

```markdown
## Designer Status Report

**Designer:** <name>
**Date:** <date>
**Capacity:** <Low | Moderate | High | Out>

---

### Project N: <Project title>

| Field               | Details |
|---------------------|---------|
| **Purpose**         | <one-sentence why> |
| **Goal**            | <what we're trying to achieve in this period> |
| **Anticipated End** | <when it should land, or "ongoing"> |
| **Status / Notes**  | <multi-sentence update; what shipped, what's in flight, what's blocked> |

---
```

Repeat the project block per project. Group by goal when there are multiple
goals; flat when there is one.

## Conventions

- One row per project. Don't fragment a project into multiple rows.
- **Status / Notes** carries the substance — write it like a paragraph, not
  a bullet list. Specific names, decisions, and dates beat generic summaries.
- Mark blockers explicitly. "No blockers" is a valid value.
- Skip the well-being line; that belongs to the 1:1 format, not the status
  report.
- Keep capacity honest. Moderate is the default; flag when it deviates.

## When to use this shape

Use for **weekly** mode and any "designer status" or "Kerri update" request.
Use for **personal** mode when the user wants the report-style format rather
than a freeform summary.

For standup, 1:1, or goal modes, see the other shapes.
