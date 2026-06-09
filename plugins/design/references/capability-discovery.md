# Capability Discovery

Discover tools only when the current workflow needs them. Do not front-load
setup questions.

Classify data before requesting or using screenshots, session replay, analytics,
research evidence, transcripts, or external artifacts.

Check for:

- Figma or FigJam when the artifact lives in design tools.
- Storybook, browser, or visual regression tools when UI behavior needs runtime
  inspection.
- Jira, GitHub, GitLab, or other issue/MR tools when packaging delivery work.
- Analytics, research repositories, session replay, or survey tools when
  evidence is needed.
- Local CLI tools when they are the fastest safe way to inspect or package work.

If a capability is missing, degrade gracefully:

- use linked artifacts or screenshots when direct tool access is unavailable
- label the missing evidence or verification gap
- ask for setup only when the missing capability blocks the decision
- never invent tool results
- never persist or publish through an external tool without explicit approval
