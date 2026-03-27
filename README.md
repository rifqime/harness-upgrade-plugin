# Harness Upgrade Plugin

I built this because the messy part was never just writing code.

The messy part was everything before that.

Ideas were coming from marketing, ops, sales, research, and product. The codebases were older, scattered, inconsistently documented, and full of unwritten assumptions. Even when the idea was good, turning it into something developers could implement safely was slow and noisy.

That translation layer was missing.

So this plugin is my attempt to make that first layer better.

Not by pretending AI can replace engineering judgment.

By giving Codex a safer way to read an existing repo, understand enough of its current reality, ask the minimum clarifying questions, and draft an initial harness or a more codebase-aware spec direction.

If that helps other people, good.

If it only reflects how I like to operate, that is also fine.

## What this is

This is an opinionated Codex plugin for existing repositories.

The core job is simple:

- read an existing codebase
- identify what is missing for harness readiness
- ask focused questions instead of guessing
- draft a docs-only initial harness
- make it easier for non-engineering ideas to become developer-friendly artifacts

In practice, that means it can help create:

- an initial `AGENTS.md`
- repo maps and reading order
- architecture or system overview docs
- deploy/runbook clarification
- contributor and review guidance
- early spec or PRD-style documentation that fits the repo better than a blank-template product brief

## Why I wanted this

Across multiple products, the problem kept looking similar:

- the codebase truth lived in chat and in people’s heads
- ops and product ideas arrived far away from the implementation details
- engineers had to re-translate business intent into codebase reality every time
- AI was useful, but it often guessed wrong when the repository itself was not legible

What I wanted was not a giant autonomous builder.

What I wanted was a better operator-side workflow:

- something that can sit closer to ops, product, growth, sales, or research
- something that can inspect the current repo before proposing structure
- something that can draft a first translation layer for engineering
- something that reduces bad assumptions before work reaches the main codebase

That is what this plugin is trying to be.

## The core idea

Before AI can reliably help implement work in an older repo, the repo needs a better harness.

Without that, ideas from non-engineering teams tend to become one of two bad things:

- vague requests that developers have to reinterpret from scratch
- AI-generated specs that sound polished but do not actually match the system

The goal here is to improve that first step.

Use AI to produce a better repo-aware translation layer, not fake certainty.

## What it can actually do

This is the important part.

The real promise is narrower than "turn business ideas into production-ready implementation automatically."

What the plugin can do well:

- inspect an existing repository and its current docs
- identify harness gaps and contradictions
- ask short, high-value owner questions
- draft an initial docs-only harness
- produce more codebase-aware spec direction than a generic PRD prompt
- help operators or product people generate something engineering can react to faster

What it does not do:

- understand every legacy codebase perfectly
- replace technical review
- invent ownership, deploy policy, or architecture truth safely
- turn rough ideas directly into correct implementation plans without repo-specific clarification
- make an old codebase magically "agent-native"

So yes, the promise is aligned with the real capability if you phrase it like this:

This plugin helps create the initial harness and translation layer that makes old codebases easier for humans and AI to work with. It can also help turn cross-functional ideas into more developer-friendly, codebase-aware specs. It is not an automatic implementation engine.

## Who this is for

Primarily:

- operators
- product people
- founders
- researchers
- growth or sales-adjacent teams
- technical operators working between business context and engineering execution

Secondarily:

- engineers inheriting an older repo
- engineering leads trying to make a repo easier for AI-assisted work

This is more operator-facing than developer-facing.

The output should become easier for developers to use, but the need usually starts earlier than engineering.

## How to use it

There are two practical ways to use this repo.

### 1. Plugin mode

Install the Codex plugin and use it inside a target repository.

That is the easiest path if you want Codex to:

- inspect the repo
- run a Pass 1 harness-readiness assessment
- ask the minimum owner questions
- draft docs-only harness updates

Use this when you want a reusable workflow.

### 2. Playbook mode

Read the bundled skill and reference docs directly and adapt the workflow manually.

Use this when you want the thinking and structure, but not necessarily the plugin packaging.

## Quick start

1. Open this repository in Codex.
2. Restart Codex if needed so it picks up `.agents/plugins/marketplace.json`.
3. Open `/plugins`.
4. Install `Harness Upgrade` from the `Harness Upgrade Plugin` marketplace.
5. Open your target repository in Codex.
6. Invoke:

```text
Use $harness-upgrade to assess this repository and draft an initial harness.
```

## Home-local install

To make the plugin available across repositories:

1. Copy `plugins/harness-upgrade` into `~/plugins/harness-upgrade`.
2. Add `~/.agents/plugins/marketplace.json` with a plugin entry pointing to `./plugins/harness-upgrade`.
3. Restart Codex and install it from your personal marketplace.

Detailed package-level install notes live in [plugins/harness-upgrade/README.md](plugins/harness-upgrade/README.md).

## Repository layout

- `.agents/plugins/marketplace.json` provides a repo-local marketplace entry for testing in Codex
- `plugins/harness-upgrade` contains the installable plugin package
- `plugins/harness-upgrade/skills/harness-upgrade` contains the public skill, `$harness-upgrade`

## v1 boundaries

- docs-only harness work
- explicit approval for scope, merge, and deploy
- no product behavior changes
- no runtime or deploy changes
- no invented ownership or release policy
- no guarantee that every business idea can be turned into an implementation-ready spec without human clarification
