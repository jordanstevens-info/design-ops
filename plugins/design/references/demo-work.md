# Demo Work

Async demos are one-way walkthroughs recorded for stakeholders to watch later.
They are different from live presentations: the recording carries the setup,
context, and ask without relying on real-time questions.

Recording means a user-authored async demo or walkthrough, not a call or meeting
recording.

Use an async demo for:

- prototype walkthroughs
- design branch or MR walkthroughs
- plugin or workflow demonstrations
- Figma or coded artifact reviews
- stakeholder feedback requests
- team onboarding to a new design practice

Do not use an async demo when a live decision meeting, formal presentation,
research session, or acceptance review is required.

## Package Location

For repo-backed work:

```text
.design/demos/<topic>/
```

For non-repo work, produce the package inline or in the user's requested
destination.

## Package Files

- `demo-outline.md`: glanceable recording outline
- `distribution-blurb.md`: Slack or email text with links and feedback ask
- `feedback-questions.md`: async feedback prompts and response handling
- `assets/`: optional screenshots, clips, links, or prototype refs

## Outline Style

Write for speaking, not reading:

- short sections
- bullets and beats
- visible artifacts or links to open
- exact lines only for claims, metrics, constraints, decisions, or risks
- reminders for what not to over-explain

Avoid word-for-word scripts unless the user explicitly asks for one.

## Feedback Loop

Every demo should make the feedback path explicit:

- what kind of feedback is useful
- where to send it
- deadline or decision timing, if known
- whether feedback should become a feedback report, scope update, ticket, or
  follow-up run

Keep async demo feedback separate from user validation. Stakeholder comments are
useful input, but they are not the same as research evidence.
