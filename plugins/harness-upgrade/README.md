# Harness Upgrade Plugin

This package turns the repository playbook into an installable Codex plugin.

It is intended for existing software repositories that need an initial harness pass for mixed human and AI-assisted development. The plugin is conservative by design: it reads the repo, asks focused owner questions, and drafts docs/workflow guidance for review. It does not try to redesign the product or change runtime behavior.

## What It Includes

- a single public skill: `$harness-upgrade`
- bundled reference material derived from this repository's playbook
- a docs-only, two-pass workflow with explicit approval gates

## Installation

### Repo marketplace

This repository includes a repo marketplace entry at `.agents/plugins/marketplace.json`.

To test locally:

1. Open this repository in Codex.
2. Restart Codex if the marketplace file is new to your session.
3. Open the plugin surface with `/plugins`.
4. Install `Harness Upgrade` from the `Harness Upgrade Guide` marketplace.

### Personal marketplace

To install it for use across repositories:

1. Copy `plugins/harness-upgrade` into `~/plugins/harness-upgrade`.
2. Add or update `~/.agents/plugins/marketplace.json` so it points to that directory.
3. Restart Codex and install the plugin from your personal marketplace.

Example personal marketplace entry:

```json
{
  "name": "personal",
  "plugins": [
    {
      "name": "harness-upgrade",
      "source": {
        "source": "local",
        "path": "./plugins/harness-upgrade"
      },
      "policy": {
        "installation": "AVAILABLE",
        "authentication": "ON_INSTALL"
      },
      "category": "Productivity"
    }
  ]
}
```

## Usage

Open the target repository in Codex and invoke the skill explicitly:

```text
Use $harness-upgrade to assess this repository and draft an initial harness.
```

The skill will:

1. inspect the repo and existing workflow assets
2. run a Pass 1 discovery-only assessment
3. stop and ask only the owner questions needed to avoid guessing
4. draft Pass 2 docs only after answers and explicit approval
5. finish with a review handoff and open questions

## v1 Boundaries

- no application logic changes
- no refactoring working product code
- no runtime, backend contract, or deploy changes
- no invented ownership or release policy
- no private codebase examples

## Manual Validation

Test the plugin against at least:

- a legacy repo with little documentation
- a repo with stale or conflicting docs
- a repo that already has some harness assets

Success looks like:

- the plugin reads the repo before asking questions
- questions are short and high-value
- Pass 2 stays docs-only
- unknowns are marked pending instead of guessed
- existing docs are reconciled instead of overwritten blindly
