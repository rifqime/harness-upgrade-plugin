---
name: harness-upgrade
description: Use when you want Codex to run an opinionated two-pass harness upgrade on an existing software repository. Best for legacy or under-documented repos where hidden context makes issue -> spec -> PR work unreliable. Use with a frontier reasoning model. Do not use for product redesigns, code refactors, runtime changes, deploy changes, or generic docs cleanup.
---

# Harness Upgrade

Use this skill to run an opinionated, two-pass harness upgrade for an existing repository.

This skill is based on OpenAI's harness-engineering article and assumes a strong reasoning model. It is not a generic documentation cleanup skill. Its job is to make repo truth more explicit so humans and AI can produce better issues, specs, PRs, and reviews without guessing the architecture.

## Load The References

Read the bundled references in this order:

- Start with [references/playbook.md](references/playbook.md) for operating stance, definition of done, and the quality bar.
- Use [references/pass-1.md](references/pass-1.md) when running discovery and clarification.
- Use [references/owner-handoff.md](references/owner-handoff.md) after the repo owner or main dev answers questions.
- Use [references/pass-2.md](references/pass-2.md) only after you have owner answers or explicit approval to proceed with pending items clearly marked.
- Use [references/checklists.md](references/checklists.md) before finalizing.

## Workflow

### 1. Establish The Operating Model

- Load [references/playbook.md](references/playbook.md).
- Keep the workflow opinionated: document reality, preserve human approval, and refuse to paper over missing truth with clean-sounding guesses.

### 2. Ground In The Repository

- Read the repository before asking questions.
- Inspect repo structure, manifests, configs, env usage, deploy files and scripts, CI, key entrypoints, contributor docs, and any existing harness assets.
- Reuse and audit current docs instead of assuming the repo is unharnessed.
- Infer facts from the repo first. Do not ask questions that can be answered by inspection.

### 3. Run Pass 1

- Follow [references/pass-1.md](references/pass-1.md).
- Compare the repo against the minimum harness baseline in that reference.
- Produce the assessment, repo facts, contradictions, and the minimal owner-question set.
- Even if the user asks to "just build the harness," do Pass 1 first unless owner answers already exist.

If owner answers are not yet available, stop after Pass 1 and wait for them.

### 4. Reconcile Owner Answers

- Follow [references/owner-handoff.md](references/owner-handoff.md).
- Compare owner answers with the repository and current docs.
- Call out only real contradictions that affect the harness.
- Do not proceed to doc changes unless the user explicitly approves Pass 2 or explicitly asks you to continue with pending items marked.

### 5. Run Pass 2

- Follow [references/pass-2.md](references/pass-2.md).
- Create or update docs and lightweight workflow scaffolding only.
- Make the repo easier for engineers, contributors, future AI agents, and cross-functional people preparing repo-aware requests.
- Replace stale docs when the repository contradicts them.

### 6. Review Handoff

- Review the result against [references/checklists.md](references/checklists.md) before finalizing.
- Call out remaining open questions.
- Call out deferred items that were intentionally left out.
- Summarize the harness changes and list the files added or updated.

## Non-Negotiables

- Do not change application logic.
- Do not refactor working product code.
- Do not change backend contracts, runtime behavior, deploy behavior, or environment behavior.
- Do not treat this as a generic docs polish task.
- Do not invent ownership, deploy rules, or release policy the owner has not approved.
- Do not downgrade strong repo evidence into vague, generic suggestions.
- Keep examples repo-agnostic and safe for public reuse.
- Treat OpenAI guidance as a reference baseline, not a mandatory operating model.

## Expected Outputs

- Pass 1: assessment, repo facts, contradictions, and a minimal owner-question set.
- Pass 2: docs-only harness draft with explicit pending items where facts remain unknown.
- Final handoff: summary of changes, files touched, open questions, and deferred work.

If the current request is only for discovery, stop after Pass 1 instead of pushing ahead into doc edits.
