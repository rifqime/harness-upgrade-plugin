# Pilot And Review Checklists

## Pilot Readiness

Use the workflow first on repositories that are:

- legacy, under-documented, or hard to onboard into
- stable enough to observe current behavior
- not in the middle of an incident or major migration
- owned by someone available to answer Pass 1 questions

Before Pass 2 begins, confirm:

- one clear repo owner is available
- one reviewer is assigned
- merge and deploy authority are known
- the team agrees the initial effort is docs-only
- a frontier reasoning model is available if the team wants the highest-quality initial pass

## Review Checklist

### Pass 1

- did the agent read the repo before asking questions
- did it inspect key entrypoints, env usage, deploy files, CI, and current workflow assets
- did it reuse or audit existing docs instead of assuming nothing existed
- did it compare the repo against a real harness baseline instead of hand-waving at "better docs"
- are the questions limited to high-impact gaps
- are the questions grouped clearly
- did it avoid proposing implementation changes

### Pass 2

- did the agent keep the work docs-only
- does the harness describe the system as it works today
- does it avoid generic boilerplate that is not supported by the repo
- are source-of-truth rules explicit
- are deploy and staging rules explicit
- are architecture boundaries explicit
- are safe and sensitive areas explicit
- are ownership and approval points explicit
- are unknowns marked as pending rather than invented

### Outcome Quality

- could a new engineer navigate the repo without hidden chat context
- could a freelance contributor follow the workflow safely
- could an AI agent draft a directionally correct issue, spec, or PR
- could an operator or product person prepare a more repo-aware request before it reaches engineering
- was product behavior preserved
