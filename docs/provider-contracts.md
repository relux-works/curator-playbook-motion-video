# Draft tool provider contracts

The canonical [provider contracts](../tools/motion-tools/references/contracts.md) travel inside [motion-tools](../tools/motion-tools/SKILL.md), outside the role collection (§8.5). They specify every command's reads, candidate location and printed outcome keys, the automatic-chain manifest convention, measurement/privilege rules, source rework and runtime prerequisites. The provider is a draft contract; it contains no executable implementation or Curator manifest.

Read the provider's local [quality checks](../tools/motion-tools/references/quality-checks.md) too. HyperFrames is the kit's intended reference renderer; it and all dependencies must be pinned and vendored by a future audited provider. No unpinned npx fetch or dummy shim is an installation path. The installed provider's links all remain inside its directory; role-to-kit asset addressing remains README gap 9.
