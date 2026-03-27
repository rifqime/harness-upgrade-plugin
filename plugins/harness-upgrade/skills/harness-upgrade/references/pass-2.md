# Pass 2

Pass 2 is docs and lightweight workflow scaffolding only.

## Allowed Outputs

- `README`
- `AGENTS.md`
- repo map / reading order
- architecture or system overview docs
- deploy or runbook docs
- env or setup docs
- issue/spec/ADR guidance
- PR and review checklists
- lightweight docs or workflow validation

## Not Allowed

- product behavior changes
- backend contract changes
- deploy behavior changes
- broad dependency churn unrelated to harnessing

## Pass 2 Requirements

Document the system as it actually works today, not as an idealized redesign.

Make these explicit whenever the repo supports them:

- what the system is
- current live workflows
- source-of-truth rules
- deploy and staging flow
- architecture boundaries
- safe versus sensitive areas
- ownership of merge and release
- how work should move from issue to spec or ADR to PR

## Pass 2 Final Output

Include:

- summary of the harness changes
- list of files added or updated
- any remaining open questions
- deferred items intentionally left out
