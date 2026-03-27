# Harness Upgrade Plugin

This repository publishes the `harness-upgrade` Codex plugin as a standalone package.

The plugin is designed for existing software repositories that need a safer first-pass harness upgrade for mixed human and AI-assisted development. It is conservative by design: it reads the repo, asks focused owner questions, and drafts docs/workflow guidance for review. It does not try to redesign the product or change runtime behavior.

## Repository Layout

- `.agents/plugins/marketplace.json` provides a repo-local marketplace entry for testing in Codex
- `plugins/harness-upgrade` contains the installable plugin package
- `plugins/harness-upgrade/skills/harness-upgrade` contains the single public skill, `$harness-upgrade`

## Quick Start

1. Open this repository in Codex.
2. Restart Codex if needed so it picks up `.agents/plugins/marketplace.json`.
3. Open `/plugins`.
4. Install `Harness Upgrade` from the `Harness Upgrade Plugin` marketplace.
5. In any target repository, invoke:

```text
Use $harness-upgrade to assess this repository and draft an initial harness.
```

## Home-Local Install

To make the plugin available across repositories:

1. Copy `plugins/harness-upgrade` into `~/plugins/harness-upgrade`.
2. Add `~/.agents/plugins/marketplace.json` with a plugin entry pointing to `./plugins/harness-upgrade`.
3. Restart Codex and install it from your personal marketplace.

The plugin package already includes its own detailed install and validation notes in [plugins/harness-upgrade/README.md](plugins/harness-upgrade/README.md).

## v1 Boundaries

- docs-only harness work
- explicit approval for scope, merge, and deploy
- no product behavior changes
- no runtime or deploy changes
- no invented ownership or release policy
