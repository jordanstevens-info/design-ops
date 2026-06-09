# Upgrade Model

`work-os:init-os` owns setup and upgrade writes. Local `work-os-audit` detects
version drift and recommends running init-os, but audit does not modify files.

## Manifest

The target manifest lives at:

```text
context/knowledge/work-os/manifest.json
```

The bundled template lives at:

```text
templates/work-os/manifest.template.json
```

The bundled manifest's `skills` map is the version registry: it records the
version each bundled template ships at. The local manifest's `skills` map
records the version each installed skill was last set to. Skill `SKILL.md`
files carry no version of their own, so version drift is read from the two
manifests and confirmed against the actual files.

On upgrade:

1. Read local manifest when present.
2. Compare `workOsVersion` and per-skill versions: bundled manifest version
   versus local manifest version for each skill.
3. Compare local `SKILL.md` files with bundled `local-skills/<skill>.md`
   templates.
4. Compare `.agents/skills/` and `.claude/skills/` copies.
5. Classify each skill as `missing`, `same`, `local-edited`, or
   `template-newer`. A skill is `template-newer` only when the bundled manifest
   version exceeds the local manifest version; confirm with a content diff
   before proposing a replacement. Compare version strings component-wise as
   integers (semver major.minor.patch), not as strings; `0.10.0` is greater
   than `0.9.0`.
6. Propose an upgrade plan with exact file actions.
7. Apply only approved replacements, additions, merges, and manifest updates,
   then set the local manifest `skills` versions to the bundled versions for
   every skill that was installed or replaced.

## Local Skill Upgrade Policy

- Upgrade audit is read/propose first. Do not rewrite existing local skills
  until the user approves the exact action set.
- Missing skill: propose install. `work-os-audit` is not special; install it
  only after explicit approval.
- Same skill: propose no file change.
- Existing skill with local edits or mismatched `.agents`/`.claude` copies:
  show the diff and preserve local files by default.
- Existing skill whose bundled manifest version exceeds the local manifest
  version: show the version delta and a focused content diff, then propose
  `keep local`, `replace from template`, or `merge manually`.
- Apply approved changes one skill at a time or as one explicitly approved
  set; never treat `upgrade` as blanket replacement permission.

The manifest is a guide, not proof that local files are unchanged. Inspect the
actual files before replacing them.
