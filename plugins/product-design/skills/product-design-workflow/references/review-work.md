# Review Work

`/pd-review` is a router. It classifies the target, then runs the right review.

## Target Types

- **MR/PR:** design acceptance review.
- **Branch/current work:** pre-submit design QA.
- **Ticket:** backlog readiness and acceptance clarity.
- **Prototype:** design critique and exploration gaps.
- **Figma/static design:** implementation-readiness and state coverage.
- **Another designer's work:** critique with feedback questions and risks.

## Output Format

1. Findings ordered by severity
2. Missing evidence or blockers
3. Acceptance/readiness/critique summary

## Review Dimensions

- Visual hierarchy and alignment
- Responsive behavior
- Accessibility basics
- Interaction states
- Copy and content edge cases
- Token and component usage
- Scope and acceptance clarity
- Risk to users, teams, or implementation

The main workflow owns target classification and final formatting. Delegate the
critique pass to `design-reviewer` when available.
