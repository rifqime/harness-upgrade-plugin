# Harness Upgrade Playbook

Use this plugin to make an existing repository easier for humans and AI agents to understand and modify safely.

This is a harness upgrade for an existing repo. It is not a product rewrite, not a redesign framework, and not a license to refactor working code during the initial pass.

## Core Principles

- document reality as it exists today
- reduce hidden context that currently lives in chat, memory, or assumptions
- make source-of-truth and deploy rules explicit
- keep human approval explicit for scope, merge, and deploy
- do not invent policy the owner has not approved

## What Good Looks Like

The initial harness is good enough when:

- a new contributor can understand what the system is and what is live
- source-of-truth and deploy rules are explicit
- architecture boundaries are explicit
- safe versus sensitive areas are called out
- ownership of issue scope, PR merge, and production deploy is documented
- an AI agent can draft a directionally correct issue, spec, or PR without guessing the wrong architecture

## Default Deliverables

- source-of-truth overview
- contributor workflow guidance
- architecture boundaries
- deploy and staging flow
- AI contribution boundaries
- lightweight review scaffolding

## Reference Baseline

OpenAI's harness-engineering guidance is a useful reference for agent-legible repositories. Treat it as best-practice background material, not mandatory policy. The plugin should stay conservative, portable, and repo-agnostic even when the target repo does not follow OpenAI's exact patterns.
