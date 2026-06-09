# Review Work

`review` classifies the target, then runs the right design review.

## Target Types

- **MR/PR:** design acceptance review.
- **Branch/current work:** pre-submit design QA.
- **Ticket:** backlog readiness and acceptance clarity.
- **Prototype:** classify rough exploratory vs. implementation-intent, then
  review exploration gaps or system fit accordingly.
- **Figma/static design:** implementation-readiness and state coverage.
- **Another designer's work:** critique with feedback questions and risks.

## Output Format

1. Findings ordered by severity
2. Missing evidence or blockers
3. Acceptance/readiness/critique summary
4. Stop condition and feedback report summary when useful

For MR/PR targets, include a merge recommendation:

- Ready for merge
- Approve with non-blocking design debt
- Block merge until required changes are made
- Request design branch before merge
- Needs formal decision owner or approver

## Review Dimensions

- Visual hierarchy and alignment
- Responsive behavior
- Accessibility basics
- Interaction states
- Copy and content edge cases
- Token and component usage
- Scope and acceptance clarity
- Risk to users, teams, or implementation

## Data Boundary

Stop as `Prohibited` if the target contains known or suspected C4 data. Do not
quote, summarize, redact, or classify underlying C4 content in the review.

The `review` skill owns target classification and final formatting. When the
runtime supports subagents, an optional fresh-context critique pass can reduce
bias; see `optional-delegation.md`.
