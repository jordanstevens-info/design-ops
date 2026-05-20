# MR Package

`/create-mr` creates a review package from a design branch. It does not merge,
deploy, or create an MR through an API.

## Workflow

1. Read `.design/README.md` and `.design/changelog/`.
2. Confirm source design branch and primary branch.
3. Collect external references from changelog entries.
4. Show scope options:
   - Code only
   - Code plus selected artifacts
   - Everything
5. Cut a clean review branch from primary.
6. Apply selected files from the design branch.
7. Commit the package.
8. Present MR title, description, test plan, and file list.
9. Push only after user approval.
10. Provide a pre-filled MR URL.

## Boundaries

- Keep the design branch intact.
- Ask before including `.design/tmp/`.
- If `.design/changelog/` is missing, ask for context before drafting.
- Do not suggest backlog tickets or unrelated next steps.
