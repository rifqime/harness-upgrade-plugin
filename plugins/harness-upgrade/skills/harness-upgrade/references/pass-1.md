# Pass 1

Pass 1 is discovery and clarification only.

## Allowed

- read the repo structure, manifests, configs, docs, CI, deploy files, and contributor instructions
- inspect current docs and workflow assets
- identify missing, stale, or contradictory repo guidance
- ask only the questions needed to build an accurate harness

## Not Allowed

- application logic changes
- refactoring working code
- runtime, deploy, or environment changes
- creating harness files before clarification

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
- ask only high-impact questions
- do not ask vague opinion questions
- do not ask questions already answerable from the repo
- if the repo already has `AGENTS.md`, docs, templates, or workflow checks, audit and reconcile them rather than assuming the repo is unharnessed
