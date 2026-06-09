# Prototype Work

`prototype` creates a coded artifact for learning. It may be disposable,
production-like, or repo-backed.

## Mode Selection

Explicit flags win:

```text
prototype --sandbox
prototype --in-repo
```

Without a flag:

- `.design/` exists: repo-backed prototype by default.
- App repo signals but no `.design/`: ask sandbox or in-repo.
- No repo/app signals: sandbox prototype by default.

## Sandbox Prototype

Use when the user needs speed, options, or a greenfield exploration. Keep it
clearly disposable. Fake data and shortcuts are allowed if labeled.

## Production Facsimile

Use when the idea needs product-like fidelity without touching production code.
Match the shape of real UI patterns, data density, and interaction constraints,
but do not pretend the result is mergeable.

## Repo-Backed Prototype

Use when real repo context matters or `.design/` already exists. Save durable
prototype artifacts under `.design/artifacts/`. Use `.design/tmp/` only for
throwaway scratch files.

## Output

State:

- Chosen mode
- Entry mode and artifact state
- What is real vs fake
- What production assumptions were copied
- What questions the prototype is meant to answer
- Whether the prototype is rough exploratory or implementation-intent
- What evidence is needed before implementation planning

Rough exploratory prototypes should not receive final design-system acceptance.
Use design-system guidance only to name future constraints. Implementation-intent
prototypes should select a design-system profile and run exploratory or strict
acceptance based on maturity and risk.

Stop as `Prohibited` if source material is known or suspected C4.
