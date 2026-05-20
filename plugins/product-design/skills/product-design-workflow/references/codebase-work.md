# Codebase Work

`/pd-engineer` implements design work in the real codebase on a `design/<topic>`
branch. It preserves branch-scoped `.design/` context, verifies the work, and
stops before MR packaging. The user invokes `/pd-create-mr`, `/pd-create-ticket`, or
`/pd-slack-update` separately when ready.

## Shortcuts

| Trigger | Action |
|---------|--------|
| Start, Preflight, Prime | Follow `context-bootstrap.md` if needed, inspect context, report readiness |
| Checkpoint | Verify build + lint pass, commit, write changelog entry, update Current State, keep working |
| Design Review, Design QA | Run the verification checklist only |
| Status | Read changelog + README, run `git status`, check primary-branch divergence, report |
| Shutdown, Wrap-Up, Finish, Retro | Run Shutdown Procedure and report against Exit Criteria |

## Branching

1. Create `design/<feature-name>` from the primary branch.
2. All `/pd-engineer` work happens on that branch. Never commit directly to the
   primary branch.
3. Agents or workers that edit code should use isolated worktrees when available.

## Boundary

`/pd-engineer` ends at verified design-branch work. Never:

- Create PRs, MRs, or merge requests.
- Suggest creating PRs, MRs, or merge requests during this flow.
- Suggest backlog tickets or next steps beyond the current task.
- Reference MR/PR workflows in the final output.

The handoff is explicit: `/pd-create-mr` packages a review branch, `/pd-create-ticket`
creates backlog-ready work, and `/pd-slack-update` drafts a team update.

## Principles

- `.design/` is branch-scoped portable context. It travels with the branch.
- Build clean. Use spikes as reference, but do not migrate spike code forward.
- Do not duplicate product-thinking docs inside implementation files.
- Visual fidelity and accessibility are exit gates, not polish steps.
- Prefer existing modules, components, tokens, helpers, and repo conventions.
- Keep scope narrow and remove dead spike code.

## Workflow

If `.design/` does not exist, follow `context-bootstrap.md` first. If `.design/`
exists, run the migration check, read `.design/README.md`, then start at step 1.

### Migration

Rename old conventions silently if found:

| Old | New |
|-----|-----|
| `.design/CLAUDE.md` | `.design/README.md` |
| `.design/changes/` | `.design/changelog/` |

Use `git mv` and record the migration in the next changelog entry.

### 1. Inspect

- Read `.design/README.md` for knowledge routing.
- Read `.design/changelog/` for prior session context.
- Locate existing components, tokens, helpers, and conventions.
- If Figma tools are available and relevant, inspect the target file or frame
  before coding.

### 2. Scope

- Check phase or milestone in architecture docs or `.design/knowledge/`.
- Check latest status in `.design/changelog/`.
- Confirm what is in scope for this branch.
- Do not pull future-phase work unless it is trivially small and directly
  unblocking the current task.

On the Status shortcut, also run:

```bash
git status
git fetch origin
git rev-list HEAD..origin/main --count
```

If the primary branch is ahead, report the count and flag that a rebase may be
needed. Do not rebase automatically.

### 3. Landing Zone

- Prefer existing modules/files over new ones.
- Prefer extending existing components over creating new ones.
- Only create new structure when architecture requires it and scope demands it.
- Use `.design/artifacts/` for prototypes, spikes, and exploratory work worth
  keeping.
- Use `.design/tmp/` for throwaway scratch files only. It should be gitignored.

### 4. Source-of-Truth Layer

Work bottom-up through the design dependency stack:

1. Design tokens: colors, spacing, typography, elevation, motion.
2. Base/primitive components: buttons, inputs, icons, badges.
3. Composed components: cards, forms, navigation, modals.
4. Page layouts/views.

Never hardcode raw color, spacing, or font values when a token exists. If a
needed token is missing, flag it and document the gap in `.design/artifacts/`.

### 5. Verify and Document

Verify against the design spec:

- Visual match: spacing, color, typography, alignment.
- Responsive behavior at key breakpoints.
- Accessibility: contrast, focus order, semantic HTML, ARIA.
- Dark mode or theme variants, if applicable.
- Component isolation: works standalone.
- Build/test/lint commands from `.design/README.md`.

Output a numbered verification checklist. Each item must include the exact
command or action and the expected outcome. Tailor it to the work: browser
inspection, DevTools token checks, keyboard navigation, Figma overlay, or
component isolation.

Write a dated `.design/changelog/` entry using
`templates/design-context/changelog-entry.md`:

- Files, components, and routes touched.
- What changed.
- What was deferred.
- External references: Jira, Figma, Confluence, research links. Downstream
  commands read these.

Graduate durable patterns. Ask: would a future agent or developer on a different
branch benefit from this? If yes, promote it:

- `design-system.md`: component patterns, token conventions, icon strategies.
- `standards.md`: process decisions and tooling conventions.

Good graduation examples:

- Use `FgtTooltip` over Flowbite Tooltip.
- Inline SVGs for Heroicons due to `TS7016`.
- Commit format is `type(scope): description`.

Do not graduate one-time design choices, incidental implementation details, or
session preferences.

Update `## Current State` in `.design/README.md` on Checkpoint and Shutdown. It
should be a cumulative 1-3 line summary of total branch progress. Replace the
old summary; do not append a diary.

Update `.design/knowledge/` if new durable patterns were established. Save
artifacts to `.design/artifacts/`. Never remove `.design/tmp/` contents without
user confirmation.

## Rules

Never do these unless the task explicitly requires it:

- Refactor broadly or add future-phase complexity.
- Introduce new dependencies without discussion.
- Commit to the primary branch.
- Remove existing tests or checks.
- Deviate from Figma specs without flagging it.
- Hardcode raw color, spacing, or font values when tokens exist.
- Override component-library defaults without justification.
- Skip accessibility verification.
- Commit `.design/tmp/` contents.
- Create empty directories. Create `changelog/`, `artifacts/`, and `tmp/` on
  first use.
- Leave dead code, commented-out blocks, unused imports, or leftover spike code.
- Rewrite a file from scratch without flagging it first. Prefer targeted edits.
- Fix, refactor, or improve code you encounter unless it blocks the current task.
- Create a new function, type, utility, or component without searching the repo
  first.

Commit sizing: prefer small commits scoped to one logical change. Use Checkpoint
to commit incrementally during the session. Squash-on-merge can clean history
later.

Reading strategy: understand file structure before reading implementations. Do
not rely on one linear pass through a file; make sure you understand the whole
file regardless of length.

Build early, build often: run the build after any structural change. Do not stack
new work on broken code.

No commit without green build: run the project build and lint commands from
`.design/README.md` before every Checkpoint or Shutdown commit. If either fails,
fix first, then commit.

Code volume check: if you are adding significantly more lines than removing,
stop and question the approach. Prefer reusing and extending existing code over
writing net-new code.

Decision rules:

- Repo has a pattern: adapt it, do not invent a new one.
- Change touches production code: choose the least invasive path.
- Feature can be deferred without blocking scope: defer.
- Two valid paths: choose the one that preserves optionality.
- Uncertain about direction: consult `.design/README.md` knowledge sources.
- Uncertain about visual intent: consult Figma before guessing.
- Token missing: flag it, do not hardcode.
- Component exists in the library: extend or compose it, do not rebuild it.
- Repo has knowledge files: reference them, do not duplicate them into
  `.design/knowledge/`.
- Search the repo before creating anything new.

## Shutdown Procedure

### Phase 1: Verify

Run all checks. If any fail, fix and re-run all checks from the top. Do not
proceed to Phase 2 until every check passes.

1. Build command passes.
2. Lint command passes.
3. Visual match passes for spacing, color, typography, alignment.
4. Responsive behavior passes at key breakpoints.
5. Accessibility passes for contrast, focus order, semantic HTML, ARIA.
6. Component isolation works standalone.
7. No dead code remains.

Output a numbered pass/fail checklist. On any failure, fix, then restart at
check 1.

### Phase 2: Document

Run once after Phase 1 is green:

8. Write a dated `.design/changelog/` entry with changed, deferred, and
   references sections.
9. Promote durable patterns to `design-system.md` or `standards.md`.
10. Replace `## Current State` in `.design/README.md` with a cumulative summary.

### Phase 3: Close

Run once after Phase 2:

11. Stage and commit with a descriptive message.
12. If a git remote exists and the user has not forbidden it, push the design
    branch to remote. Do not open or create an MR.
13. Report against each Exit Criteria item and flag unsatisfied items.

## Exit Criteria

All must be true:

1. Requested work functions end to end.
2. Change is scoped with no unrelated modifications.
3. Visual output matches design spec for spacing, color, typography, alignment.
4. Accessibility basics pass: contrast, focus order, semantic HTML, ARIA.
5. `.design/changelog/` entry documents changes and deferrals.
6. `## Current State` in `.design/README.md` reflects cumulative branch progress.
7. Durable patterns graduated to knowledge files where appropriate.
8. Next step is clearer than before.

Items 3 and 4 are hard gates. Do not mark work done until verified.

## References

- `context-bootstrap.md`: repo setup, detection, `.design/` creation, and
  interview flow.
- `templates/design-context/`: README, vision, architecture, standards,
  design-system, and changelog templates.
