# Design Story

`/pd-create-preso` builds a presentation package around the design story.

## Location

For repo-backed work:

```text
.design/presos/<topic>/
```

For non-repo work, produce the artifact inline or in a user-specified location.

## Story Sections

- Problem statement
- Current state
- Research plan and/or findings
- Design exploration
- Recommended direction
- Feedback questions
- Impact and success signals
- Demo path
- Decision needed

## Package Files

- `design-story.md`: narrative spine
- `one-pager.md`: async shareable summary
- `deck-outline.md`: slide-by-slide outline
- `demo-script.md`: live walkthrough script
- `assets/`: screenshots, clips, links, or prototype references when available

## Principle

The preso should connect design rationale to the artifact: Figma, coded
prototype, real branch, MR package, or ticket.
