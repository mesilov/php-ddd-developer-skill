# Preparing and publishing releases

Preparation, integration, tagging and publication are distinct actions. Complete
the stages covered by the user's request and existing authorization.

## Discover release capability

Inspect the remote's current branches, tags, releases and CI, then the actual
product tree, version metadata, builder and workflows. This maintainer setup
does not create the installable PHP DDD skill or a release pipeline.

If a required product, version convention or builder is absent, identify that
gap and prepare a concrete proposal or implement it when authorized. Do not
invent executable commands, artifact names, a PHP baseline or a release-ready
status. Maintainer-only edits do not justify bumping a product version.

## Select and prepare a candidate

Choose the full intended commit SHA and inspect its complete diff/tree. Enumerate
accumulated changes before integration. For a version bump, update every actual
version declaration, relevant tests, current documentation and release notes
together. Source review dates change only after review; preserve historical
version strings in past reports.

Run [checks](checks.md) and any applicable source verification. Build from a clean
checkout of the final release SHA, using the repository's real builder and a
fresh output directory. If integration changes the candidate, repeat affected
checks and rebuild. Inspect terminal mandatory CI for that SHA before claiming
CI success. If CI does not exist, report its absence and use the agreed release
requirements instead of silently treating it as green.

Record the exact asset names, archive contents, checksums, toolchain and candidate
SHA. Prepare notes describing coverage, compatibility, sources and verification
limits. A successful local build proves neither remote CI nor publication.

## Publish when authorized

Read back any existing remote tag and release first. Follow established tag
naming; state the selected convention if this is the first release. Create a new
tag on the exact reviewed SHA only within an authorized tagging/release task.

Verify the remote tag resolves to that SHA, including peeling annotated tags.
Use supported forge tools or the installed CLI's documented interface, attaching
only the explicit candidate files. Avoid implicit tagging of the default branch,
stale wildcard assets and unintended latest/prerelease settings.

After publication, read back the release URL, tag target, draft/prerelease status
and expected asset names/sizes. Download to a fresh directory and use the
[asset checks](checks.md) to compare bytes and checksums with the reviewed candidate
and tagged product. A draft is not a published release. Report the furthest
confirmed stage if readback or downloads fail.

## Existing tag or partial publication

After an unknown creation/upload result, inspect remote state before retrying.
Record tag target, release status, assets and digests; make a bounded corrective
attempt only within the authorized scope. Stop blind retries and report unresolved
state with the evidence already collected.

Do not silently move an existing tag or overwrite published assets. For changed
published content, prefer a corrected version. If replacement is explicitly
requested, enumerate the exact tag/assets and consequences, respect immutability,
then verify the resulting remote state and downloaded bytes.
