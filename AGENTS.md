# Repository instructions

Use [php-ddd-skill-maintainer](.agents/skills/php-ddd-skill-maintainer/SKILL.md)
for repository maintenance, source reviews, package checks, pull requests and
releases. Its canonical files live in `.agents/skills/`; Codex and Claude
aliases must point there rather than duplicate the instructions.

This repository develops a PHP DDD skill package. Inspect the current tree
before using product, validation or release paths; maintainer setup alone
does not provide those capabilities.

## Current library documentation

Use Context7 MCP for library, framework, SDK, API, CLI or cloud-service
documentation, including syntax, configuration, setup, migration and
library-specific debugging. Prefer it over web search even for familiar tools.

1. Start with `resolve-library-id`, including the library name and the
   documentation question, unless an exact `/org/project` ID was provided.
2. Select by exact name, relevance, source reputation, snippet coverage and
   benchmark score. Retry with an alternate name/query if necessary; prefer
   a version-specific ID when a version was requested.
3. Use `query-docs` for one concept at a time with the selected ID. Combine
   concepts only when the question concerns their interaction.
4. Base the answer on the retrieved documentation.

Context7 is unnecessary for general programming concepts, refactoring,
scripts written from scratch, business-logic debugging or code review
that does not require library documentation.
