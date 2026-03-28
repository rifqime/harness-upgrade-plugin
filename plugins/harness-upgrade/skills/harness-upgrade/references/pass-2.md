# Pass 2

Pass 2 is docs and lightweight workflow scaffolding only.

Use:

- repository contents
- current docs and workflow files
- owner clarification answers
- the OpenAI harness-engineering article as a reference baseline

to create the initial harness-engineering layer for the repository.

## Operating Rule

Document the system as it actually works today, not as an idealized redesign.

If existing docs are stale, misleading, or contradicted by the repo, replace or rewrite them with accurate versions.
If a policy or workflow is still unknown, mark it as pending instead of inventing it.

## Audience

Make the repository easier for:

- core engineers
- external or freelance contributors
- future AI agents
- operators or product-adjacent people who need to turn ideas into repo-aware issues or specs

## Required Explicitness

Make these explicit whenever the repo supports them:

- what the system is
- current live workflows
- source-of-truth rules
- deploy and staging flow
- architecture boundaries
- safe versus sensitive areas
- ownership of merge and release
- how business or operator requests should become issue -> spec or ADR -> PR

## Allowed Outputs

- `README`
- `AGENTS.md`
- repo map / reading order
- architecture or system overview docs
- deploy or runbook docs
- env or setup docs
- issue taxonomy or request intake guidance
- spec or ADR guidance
- PR template or checklist
- review checklist
- lightweight docs or workflow validation

## Not Allowed

- product behavior changes
- backend contract changes
- deploy behavior changes
- broad dependency churn unrelated to harnessing
- inventing ownership, release policy, or approval rules the owner did not approve
- smoothing over real ambiguity just to make the harness look complete

## Pass 2 Final Output

Include:

- summary of the harness changes
- list of files added or updated
- any remaining open questions
- deferred items intentionally left out
