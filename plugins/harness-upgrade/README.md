# Harness Upgrade Plugin

This package turns an opinionated harness workflow into an installable Codex plugin.

I built it for a messy but common problem: ideas come from ops, marketing, sales, research, and product, but older codebases are hard to translate those ideas into safely. This plugin is meant to create the first repo-aware translation layer, not to pretend the repo is already clean or agent-ready.

The plugin is conservative by design: it reads the repo, asks focused owner questions, and drafts docs/workflow guidance for review. It does not try to redesign the product or change runtime behavior.

## What It Includes

- a single public skill: `$harness-upgrade`
- bundled reference material derived from this repository's playbook
- a docs-only, two-pass workflow with explicit approval gates

## What The Promise Really Is

Use this plugin when you want Codex to help:

- make an older repo more harness-compatible
- create a first AI translation layer between cross-functional ideas and the actual codebase
- draft developer-friendlier specs or harness docs that reflect repo reality better than generic planning prompts

Do not use it as if it can automatically convert business ideas into correct implementation plans without review. The output should be treated as a stronger starting point for engineering, not as final truth.

## Installation

### Repo marketplace

This repository includes a repo marketplace entry at `.agents/plugins/marketplace.json`.

To test locally:

1. Open this repository in Codex.
2. Restart Codex if the marketplace file is new to your session.
3. Open the plugin surface with `/plugins`.
4. Install `Harness Upgrade` from the `Harness Upgrade Plugin` marketplace.

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

This is most useful when the request starts outside engineering, but the output needs to land closer to engineering reality.

## v1 Boundaries

- no application logic changes
- no refactoring working product code
- no runtime, backend contract, or deploy changes
- no invented ownership or release policy
- no private codebase examples
- no promise that every ops or product idea can be converted into an implementation-ready spec without clarification

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
