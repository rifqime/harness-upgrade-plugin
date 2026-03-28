# Pass 1

Pass 1 is discovery and clarification only.

Use this pass to understand the repository as it exists today and to decide what must be clarified before any harness docs are written.

## Before Starting

- read the repository's current source-of-truth docs, contributor guidance, deploy docs, and any existing harness assets
- use the OpenAI harness-engineering article as a reference baseline for agent-legible repos
- assume the repo may already have partial harness material; audit and reconcile it before declaring gaps

## Required Discovery

Read enough of the repository to understand its current reality:

- repository structure and major directories
- manifests, configs, env usage, and key entrypoints
- deploy files, scripts, CI, and runtime boundaries
- contributor docs, workflow docs, and ownership signals
- existing `README`, `AGENTS.md`, templates, runbooks, checklists, or validation scripts

## Minimum Harness Baseline

Compare the repo against this baseline:

- concise `AGENTS.md` or repo map
- source-of-truth rules
- architecture boundaries
- deploy/runbook clarity
- contributor workflow
- issue/spec/ADR guidance
- PR/review expectations

## Allowed

- identify what is already good enough
- identify what is missing, stale, contradictory, or ambiguous
- infer facts from the repository itself
- ask only the clarification questions needed to build an accurate initial harness

## Not Allowed

- application logic changes
- refactoring working code
- runtime, deploy, or environment changes
- creating or editing harness files before clarification
- proposing broad redesigns or refactors as a substitute for understanding the repo

## Pass 1 Output

Produce:

- a short summary of what the repo appears to be
- a short summary of what is already good enough
- a short summary of what is missing for harness readiness
- facts inferred from the repo
- ambiguities or contradictions found
- a prioritized list of clarification questions for the main dev or repo owner

Group the questions under:

- Product truth
- Source of truth / deployment
- Architecture boundaries
- Ownership / workflow
- AI contribution boundaries
- Legacy / fragile areas

## Pass 1 Guardrails

- read the repo before asking questions
- infer what you can from the repo first
- ask only high-impact questions
- do not ask vague opinion questions
- do not ask questions already answerable from the repo
- do not let missing context become an excuse for generic boilerplate
- if the repo already has harness assets, audit and reconcile them rather than assuming the repo is unharnessed
- stop after Pass 1 if owner answers are not yet available
