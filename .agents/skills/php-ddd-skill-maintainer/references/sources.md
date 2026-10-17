# Reviewing sources and DDD coverage

Read the affected product references and any existing source manifest, source
review or third-party notices. Discover the current files; the Symfony donor
list, counts and provenance schema do not apply automatically.

## Select evidence

For a donor repository, record its URL, full commit SHA, selected paths, license
and the adopted scope. Compare old and candidate revisions, including license
changes, in separate clean checkouts. Preserve the user's source checkouts.
For an authoritative article or documentation page, record its exact URL,
applicable version and actual review date. A link or a new date alone does not
prove that its contents were reviewed.

For library, framework, SDK, API or CLI facts, follow the Context7 procedure in
`AGENTS.md`. Verify any PHP or framework version requirement against current
primary documentation. If retrieval fails, keep existing provenance and report
the missing verification; do not invent hashes, compatibility or review dates.

## Maintain the product boundary

Keep PHP DDD coverage focused on domain discovery, ubiquitous language, bounded
contexts, aggregates, invariants and domain/application boundaries. Explain when
strategic or tactical patterns are useful; do not require DDD or CQRS for every
CRUD feature.

These are defaults. Honor an explicit user choice of architecture or product
scope, state its tradeoffs, and distinguish that choice from general DDD advice.

Treat Symfony DI, Doctrine mappings, Messenger configuration and framework
runtime behavior as integration concerns. Include or cross-reference them only
where the requested PHP DDD guidance needs them. A Symfony maintainer workflow
is not a source of domain-modeling requirements.

Use original synthesis and usable source links. Before copying or adapting donor
text or examples, inspect its license and retain the required attribution and
full notices. If a manifest records file hashes, hash raw source bytes at the
pinned revision; rendered HTML and adapted guidance are different artifacts.

## Update and verify one coherent change

Update the affected guidance, provenance records, notices and changelog together.
Keep the product entrypoint concise and route detailed material to references.
Change schema, coverage expectations or version constraints only when the reviewed
scope requires it; retain checks that detect unexplained mismatches.

Run the source checks that actually exist and the relevant [package checks](checks.md).
State which upstream revisions and files were checked, what was deliberately left
pinned and what remains uncertain. Structural validation, source-byte verification
and current upstream freshness are separate claims.
