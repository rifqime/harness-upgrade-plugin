# Harness Upgrade Plugin

I made this because the hard part was usually not the coding itself.

The hard part was what happened before the coding.

Ideas were coming in from ops, marketing, sales, research, and product. The repos were older, scattered, and unevenly documented. A lot of the real context lived in chat, in habits, or in the heads of a few people who already knew how everything worked.

That meant even a good idea could get stuck in translation.

Someone still had to turn it into something engineering could actually use:

- a repo-aware spec
- a grounded PRD
- a clearer read on what the system already does
- a first pass at docs that make the codebase easier to work with

That is what this plugin is for.

It is not trying to automate product strategy or replace engineering review. It is trying to make the first translation step less messy.

## What this is

This is an opinionated Codex plugin for working with existing repositories.

It is written for frontier reasoning models and a strict two-pass workflow. It is not meant to be a generic docs helper or a one-shot planning assistant.

The job is straightforward:

- read the repo as it exists today
- figure out what is missing for a basic harness
- ask only the questions needed to avoid guessing
- draft docs-only harness material
- help turn cross-functional ideas into something closer to engineering reality

In practice, that can mean drafting:

- an `AGENTS.md`
- a repo map or reading order
- architecture notes
- deploy and runbook clarification
- contributor guidance
- review scaffolding
- an early spec or PRD that fits the actual codebase better than a generic template

## Why I wanted it

Across different products, I kept seeing the same problem.

The business side of the work and the code side of the work were too far apart.

Ops might know the process pain. Sales might know what customers keep asking for. Marketing might know the campaign idea. Product might know the direction. But turning that into something that fits a real codebase was still a separate job, and usually a messy one.

AI can help with that, but only up to a point.

If the repo is hard to read, the AI usually fills the gaps with confident guesses. That is where a lot of bad specs come from.

So the goal here is simpler than “AI builds the feature.”

The goal is to give AI enough structure to produce a better first translation layer between idea and implementation.

## The main idea

Older codebases are often not ready for agent-assisted work, even if the code itself is fine.

The missing piece is usually the harness:

- what the system is
- what is actually live
- where the boundaries are
- what is safe to touch
- what needs approval
- how work is supposed to move from idea to implementation

Once that is more explicit, both humans and AI have a better chance of producing useful work.

So this plugin starts there.

## What it can do

What it is good at:

- inspecting an existing repo and its docs
- running a strict Pass 1 before writing anything
- finding missing or conflicting harness information
- asking focused owner questions
- drafting an initial docs-only harness
- producing more codebase-aware spec direction than a blank PRD prompt
- helping operators or product-adjacent people prepare something engineering can react to faster

What it is not good at:

- understanding every legacy repo perfectly
- replacing technical review
- inventing architecture truth safely
- inventing deploy or ownership rules safely
- turning rough business ideas directly into correct implementation plans with no clarification

So the promise here is intentionally narrow:

This plugin helps create an initial harness and a better AI translation layer for older repositories. It can also help turn cross-functional ideas into more developer-friendly, codebase-aware docs or specs. It is not an automatic implementation system.

## Who this is for

Mostly:

- operators
- product people
- founders
- researchers
- growth or sales-adjacent teams
- technical generalists sitting between business context and engineering execution

Also:

- engineers inheriting an older repo
- engineering leads who want a repo to be easier to work with using AI

So yes, this leans more toward the operator side than the developer side.

The point is not that developers are the audience for the plugin itself. The point is that the output should be easier for developers to use.

## Reference, not doctrine

The main reference behind this repo is OpenAI’s harness-engineering article:

- [Harness engineering: leveraging Codex in an agent-first world](https://openai.com/index/harness-engineering/)

I think it is a useful reference. I also think it is opinionated, just like this repo is opinionated.

I am not treating that article as universal policy, and I do not think other teams should copy it blindly. I use it more as a strong example of the kind of repo legibility that helps agents do less guessing.

This plugin follows that spirit, but it stays practical:

- document reality
- do not redesign the product
- do not invent process
- keep approvals explicit

## How to use it

There are two simple ways to use this repo.

### 1. Plugin mode

Install the Codex plugin and use it inside a target repository.

This is the easier path if you want Codex to:

- inspect the repo
- run a first-pass harness assessment
- ask the minimum owner questions
- draft docs-only harness updates

### 2. Playbook mode

Read the bundled skill and reference docs directly and use the workflow more manually.

This is useful if you like the approach but do not necessarily want to depend on the plugin packaging.

## Quick start

1. Open this repository in Codex.
2. Restart Codex if needed so it picks up `.agents/plugins/marketplace.json`.
3. Open `/plugins`.
4. Install `Harness Upgrade` from the `Harness Upgrade Plugin` marketplace.
5. Open your target repository in Codex.
6. Invoke:

```text
Use $harness-upgrade to inspect this repository, run Pass 1 only, ask the minimum clarification questions, and after my answers run Pass 2 to draft the initial harness.
```

## Home-local install

To make the plugin available across repositories:

1. Copy `plugins/harness-upgrade` into `~/plugins/harness-upgrade`.
2. Add `~/.agents/plugins/marketplace.json` with a plugin entry pointing to `./plugins/harness-upgrade`.
3. Restart Codex and install it from your personal marketplace.

Detailed package-level install notes live in [plugins/harness-upgrade/README.md](plugins/harness-upgrade/README.md).

## Repository layout

- `.agents/plugins/marketplace.json` gives you a repo-local marketplace entry for testing in Codex
- `plugins/harness-upgrade` contains the installable plugin package
- `plugins/harness-upgrade/skills/harness-upgrade` contains the public skill, `$harness-upgrade`

## v1 boundaries

- docs-only harness work
- explicit approval for scope, merge, and deploy
- no product behavior changes
- no runtime or deploy changes
- no invented ownership or release policy
- no guarantee that every business idea can be turned into an implementation-ready spec without human clarification
