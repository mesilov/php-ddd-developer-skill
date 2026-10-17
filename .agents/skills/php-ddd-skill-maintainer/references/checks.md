# Repository and package checks

Run from the repository root. This is a skill repository, not a PHP application.
Inspect the current scripts, dependency declarations, tests and workflows before
selecting commands. Do not copy Symfony's Python validator/build commands or
assume Composer, PHPUnit or a particular PHP version is required.

## Before opening a PR

Commit a substantive `CHANGELOG.md` entry under `Unreleased` in the same branch.
This covers drafts, documentation, skills, tests and tooling. Create the file if
absent; preserve its format and history.

Refresh the actual target and inspect the changelog's target-to-head diff.
Existing target history, whitespace, deletion alone or an unrelated entry is
insufficient. Describe the actual effect, then commit it before opening the PR.
Recheck after scope or target changes.

When a PR is authorized, deliver the existing intended commits and read back the
PR URL, base, head SHA and changed scope. Creating a PR does not authorize merge
or release publication.

## Choose checks from the actual tree

Always review the final diff and run `git diff --check`. For new untracked files,
also inspect their complete contents and whitespace: Git's diff omits them until
they are staged.

For a skill change, check:

- YAML frontmatter, name/description and any UI metadata agree.
- Relative Markdown links resolve from their containing files.
- Codex/Claude aliases resolve to the one canonical maintainer directory.
- References distinguish existing capabilities from intended paths.
- The guidance applies to realistic maintenance requests without expanding scope.

If skill-creator is available, use its `scripts/quick_validate.py` with the
changed skill directory. It is an optional external check, not a script bundled
here. Its success proves basic skill structure; review links, aliases and behavior
separately.

Run repository validators, tests and builders only when present, using the
declared environment and supported arguments. For executable behavior changes,
use a meaningful regression check. Do not weaken an unexplained acceptance
failure. If tooling or CI is absent, report that limit; add it only when within
the task's scope.

## Package acceptance, when a product and builder exist

Inspect every archive member and its bytes against the canonical product tree.
Require the intended installable layout and exclude maintainer files, aliases,
Git metadata, credentials and unrelated generated files. Check duplicate members,
unsafe paths and unexpected links without extracting untrusted archives.

For reproducibility, build twice from the same clean candidate in the same
toolchain. Record that scope instead of promising identical compression across
all environments.

For downloaded release assets, compare exact expected names, checksums and
archive bytes with the reviewed candidate built from the final tag target.
A self-consistent checksum file alone does not tie assets to that candidate.

## Evidence and reporting

| Result | What it establishes |
| --- | --- |
| Skill structure/link/alias checks | Maintainer metadata and local discovery work |
| Source checkout verification | Selected bytes and licenses match recorded revisions |
| Product validator/tests | Only the acceptance rules those checks actually exercise |
| Builder and archive comparison | Local candidate layout, contents and digests |
| Terminal remote CI | Inspected jobs completed for the exact recorded SHA |
| Published asset readback | Remote release identity and downloaded candidate agreement |

For substantial guidance changes, exercise realistic bootstrap, source-refresh,
PR and release-recovery requests with the skill. A fresh read-only agent is useful
when available; scenarios are not proof of PHP runtime behavior.

Record commands, actual counts/results, branch/base and skipped checks. Use a
dated report under `docs/` when durable evidence is useful; preserve earlier
reports. Never report absent CI as passed or Actions artifacts as a release.
