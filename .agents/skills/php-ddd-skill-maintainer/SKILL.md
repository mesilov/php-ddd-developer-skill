---
name: php-ddd-skill-maintainer
description: Use when maintaining the php-ddd-developer-skill repository, reviewing DDD sources or provenance, changing package checks, preparing pull requests, or handling its releases.
license: MIT
---

# PHP DDD Skill Maintainer

Maintain this repository's **skill package**. For domain modeling or code changes
in a consuming PHP application, follow that application's instructions and its
installed development skills.

Adapted from [Symfony Skill Maintainer](https://github.com/mesilov/symfony-best-practices-skill/blob/fb4235e5acfd7f5c6016de43267e52bb0a2bf0a5/.agents/skills/symfony-skill-maintainer/SKILL.md)
(MIT, copyright 2026 Maksim Mesilov); see the repository's `LICENSE`.

## Establish repository context

Run `pwd`, `git status --short --branch`, `git worktree list` and
`git remote -v`. Inspect `AGENTS.md`, then the README, changelog, product
entrypoint, version files, source records, scripts, tests and CI **that exist**.

This repository starts as a bootstrap: do not assume the Symfony repository's
Python tooling, source manifest, framework versions or release workflow exists
here. Verify current capabilities before using commands or reporting coverage.

Preserve unrelated changes. Start new work from refreshed `origin/main` on a
`codex/` branch, using an isolated worktree when needed. For continuing,
reviewing or publishing existing work, retain its branch/worktree and intended
commits. Follow a requested alternative base; inspect the complete diff against
the refreshed actual target before integration.

## Package boundaries

| Path | Responsibility |
| --- | --- |
| `skills/php-ddd-developer/` | Intended installable product, once introduced |
| `.agents/skills/php-ddd-skill-maintainer/` | Canonical repository-only maintainer skill |
| `.codex/skills/`, `.claude/skills/` | Relative aliases to the canonical maintainer |
| `scripts/`, `tests/`, `.github/workflows/` | Validation, packaging and CI, when implemented |
| `docs/` | Review decisions and dated verification evidence, when needed |

Confirm the actual product layout if it evolves. Keep maintainer files and aliases
outside product archives. Maintainer-only changes do not require a product version
bump. Keep agent instructions in English; preserve existing documentation style
and answer the user in the language of the request.

## Changelog gate before every PR

Before opening any PR, including drafts and documentation changes, commit a
meaningful `CHANGELOG.md` entry for the actual change in the same branch.
An entry already in the target does not satisfy this gate. Recheck the substantive
diff when scope or target changes; follow [checks](references/checks.md).

## Read the relevant procedure

- DDD coverage, upstream updates, compatibility or licensing: [sources](references/sources.md).
- Repository edits, check failures or package acceptance: [checks](references/checks.md).
- Versions, tags, assets or publication recovery: [releases](references/releases.md), then checks.

Complete preparation and checks within the request. Execute push, merge, tagging
or publication when authorized; this skill grants no additional scope. Reuse
existing authorization without repeatedly asking.

Report branch/base, changed scope, source revisions, checks and limitations.
Distinguish local validation, source-byte verification, terminal CI, integration
and published assets. Preserve historical evidence and date new results.
