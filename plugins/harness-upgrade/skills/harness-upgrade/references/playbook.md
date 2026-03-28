# Harness Upgrade Playbook

Use this plugin to make an existing repository easier for humans and frontier AI agents to understand and modify safely.

This is an opinionated harness-upgrade workflow for existing repositories. It is based primarily on OpenAI's harness-engineering article and on practical repo upgrade work. It is not a generic documentation tidy-up checklist, not a product rewrite framework, and not a license to refactor working code during the initial pass.

## Why This Exists

- too much repo truth still lives in chat, memory, and unwritten assumptions
- older repos are harder to hand off across engineers, freelancers, operators, and AI agents
- review quality drops when architecture, deploy flow, and source-of-truth rules are implicit
- the gap between cross-functional ideas and codebase reality is often the real bottleneck
- a good harness makes issue -> spec -> PR work more reliable and more repo-aware

## Reference Baseline

Primary reference:

- OpenAI, "Harness engineering: leveraging Codex in an agent-first world"
  - https://openai.com/index/harness-engineering/

Treat that article as a strong reference for agent-legible repositories, not as a requirement to copy OpenAI's exact operating model.

## Model And Tooling Stance

This workflow is written for today's strongest reasoning models and works best in a tool-aware environment that can inspect and edit the repository directly.

- prefer frontier reasoning models for the initial harness pass
- if using OpenAI, `gpt-5.4` with `high` reasoning is the intended baseline
- weaker substitute models are more likely to ask low-value questions or produce generic harness boilerplate
- use Codex or another agentic environment that can operate directly on the repository

## Core Policy

- start with a recommended pilot, not an org-wide mandate
- use this first on legacy or under-documented repos
- keep human approval for scope, merge, and deploy
- document reality as it exists today
- do not invent policies the owner has not approved
- do not make the repo look cleaner on paper than it is in reality

## Definition Of Done

The initial harness is good enough when:

- a new contributor can understand what the system is and what is live
- source-of-truth and deploy rules are explicit
- architecture boundaries are explicit
- safe versus sensitive areas are called out
- ownership of issue scope, PR merge, and production deploy is documented
- an AI agent can draft a directionally correct issue, spec, or PR without guessing the wrong architecture
- an operator or product person can prepare a more repo-aware request before it reaches engineering

## Default Deliverables

- source-of-truth overview
- contributor workflow guidance
- architecture boundaries
- deploy and staging flow
- AI contribution boundaries
- lightweight review scaffolding
- issue/spec/ADR guidance where the repo needs it
