# MR Package

`/create-mr` cuts a clean review branch from a `design/` branch and prepares
copy-pasteable MR materials. The design branch stays intact. This command does
not merge, deploy, or create an MR through an API.

## Workflow

### 1. Read Context

- Read `.design/README.md` to understand project and branch scope.
- Read `.design/changelog/` entries to understand what was built and what was
  deferred.
- Collect external references from changelog entries: Jira tickets, Figma URLs,
  Confluence pages, research notes. Include these in the MR description.
- Run `git diff --stat <primary>..<design-branch>` to see all changed files.
- Confirm the source design branch and primary branch before changing branches.

If the design branch has no `.design/changelog/` entries, flag the missing
context and ask the user for enough detail before drafting the MR description.

### 2. Choose Scope

Present three options and wait for the user to choose:

- **Code only**: production files only, no `.design/` directory. This is the
  cleanest MR for teams that treat `.design/` as scaffolding.
- **Code + selected artifacts**: production files plus user-selected `.design/`
  files, such as a changelog entry or `design-system.md`. Use when reviewers
  need design context.
- **Everything**: all files from the design branch including `.design/`. Use for
  internal teams that want full visibility.

Ask before including any `.design/tmp/` contents.

### 3. Cut Review Branch

1. Identify the primary branch, usually `main` or `master`.
2. Create a review branch from primary.
3. Check out selected additions and modifications from the design branch.
4. Find deletions with `git diff --diff-filter=D --name-only
   <primary>..<design-branch>`.
5. Run `git rm` for deleted files that fall within the selected scope.
6. Commit the package with a descriptive message summarizing the design work.

The review branch should contain only the files selected for review. Do not
rebase, delete, or otherwise rewrite the source design branch.

### 4. Review Before Push

Present these materials before pushing:

- **MR title**: short, specific, under 70 characters.
- **MR description** using `templates/mr/mr-description.md`, including:
  - Summary: what changed and why.
  - What changed: new, modified, and removed files grouped by area.
  - Design decisions: key choices and rationale.
  - Test plan: exact verification steps and observed outcomes.
  - References: Jira, Figma, Confluence, changelog, research links.
- **File list**: all files included in the review branch.

Format the description as copy-pasteable Markdown in a fenced code block. Wait
for user approval or edits before pushing.

### 5. Push and Link

Push the branch with upstream tracking only after approval. Detect hosting from
`git remote get-url origin` and construct a pre-filled review URL.

GitLab:

```text
<remote>/-/merge_requests/new?merge_request[source_branch]=<branch>&merge_request[title]=<url-encoded-title>
```

GitHub:

```text
<remote>/compare/<primary>...<branch>?expand=1&title=<url-encoded-title>
```

Present the link so the user can open the MR form with branch and title
pre-filled, then paste the approved description. Stop there.

## Boundaries

- Keep the design branch intact.
- Never merge or deploy.
- Never create the MR through an API.
- Do not suggest backlog tickets or unrelated follow-up work.
- Do not include `.design/tmp/` without explicit approval.
- If primary branch divergence makes the package ambiguous, report it and ask
  before rebasing or rebuilding the branch.
