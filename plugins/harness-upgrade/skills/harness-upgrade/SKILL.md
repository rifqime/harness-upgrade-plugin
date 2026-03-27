---
name: harness-upgrade
description: Use when you want Codex to assess an existing software repository and draft an initial harness-engineering layer for mixed human and AI-assisted development. Best for legacy or under-documented repos that need clearer source-of-truth docs, contributor guidance, architecture boundaries, deploy/runbook clarity, and review scaffolding. Do not use for product redesigns, code refactors, runtime changes, deploy changes, or dependency churn.
---

# Harness Upgrade

Use this skill to run a conservative, docs-only harness upgrade for an existing repository.

The workflow is baseline-first: infer what you can from the repo, ask only the questions needed to avoid guessing, then draft the initial harness with explicit approval gates for scope, merge, and deploy.

## Load The References

Read the bundled references progressively:

- Start with [references/playbook.md](references/playbook.md) for scope, non-goals, and the definition of done.
- Use [references/pass-1.md](references/pass-1.md) when running discovery and clarification.
- Use [references/owner-handoff.md](references/owner-handoff.md) after the repo owner or main dev answers questions.
- Use [references/pass-2.md](references/pass-2.md) only after you have owner answers or explicit approval to proceed with pending items clearly marked.
- Use [references/checklists.md](references/checklists.md) before finalizing.

## Workflow

### 1. Ground In The Repository

- Read the repository before asking questions.
- Inspect repo structure, manifests, configs, env usage, deploy files, CI, contributor docs, and any existing harness assets.
- Reuse and audit current docs instead of assuming the repo is unharnessed.
- Infer facts from the repo first. Do not ask questions that can be answered by inspection.

### 2. Run Pass 1

- Produce a short summary of what the repo appears to be.
- State what is already good enough.
- State what is missing, stale, contradictory, or ambiguous for harness readiness.
- List facts inferred from the repo.
- Ask only the minimum clarification questions needed to create an accurate initial harness.
- Group questions under:
  - Product truth
  - Source of truth / deployment
  - Architecture boundaries
  - Ownership / workflow
  - AI contribution boundaries
  - Legacy / fragile areas

If owner answers are not yet available, stop after Pass 1 and wait for them.

### 3. Reconcile Owner Answers

- Compare owner answers with the repository and current docs.
- Call out only real contradictions that affect the harness.
- If something is still unknown, mark it as pending owner confirmation instead of inventing policy.
- Do not proceed to docs changes unless the user explicitly approves the draft-only harness pass.

### 4. Run Pass 2

Draft or update docs and lightweight workflow scaffolding only. Allowed outputs include:

- `README`
- `AGENTS.md`
- repo map / reading order
- architecture or system overview docs
- deploy or runbook docs
- env or setup docs
- issue/spec/ADR guidance
- PR and review checklists

Make these explicit wherever the repo supports them:

- what the system is
- what is live today
- source-of-truth rules
- deploy and staging flow
- architecture boundaries
- safe versus sensitive areas
- merge and release ownership
- how requests should flow from issue to spec or ADR to PR

### 5. Review Handoff

- Review the result against the bundled checklists before finalizing.
- Call out remaining open questions.
- Call out deferred items that were intentionally left out.
- Summarize the harness changes and list the files added or updated.

## Non-Negotiables

- Do not change application logic.
- Do not refactor working product code.
- Do not change backend contracts, runtime behavior, deploy behavior, or environment behavior.
- Do not invent ownership, deploy rules, or release policy the owner has not approved.
- Keep examples repo-agnostic and safe for public reuse.
- Treat OpenAI guidance as a reference baseline, not a mandatory operating model.

## Expected Outputs

- Pass 1: assessment, repo facts, contradictions, and a minimal owner-question set.
- Pass 2: docs-only harness draft with explicit pending items where facts remain unknown.
- Final handoff: summary of changes, files touched, open questions, and deferred work.

If the current request is only for discovery, stop after Pass 1 instead of pushing ahead into doc edits.
