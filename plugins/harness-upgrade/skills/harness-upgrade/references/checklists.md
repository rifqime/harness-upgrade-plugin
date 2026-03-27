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

## Review Checklist

### Pass 1

- did the agent read the repo before asking questions
- did it reuse or audit existing docs instead of assuming nothing existed
- are the questions limited to high-impact gaps
- are the questions grouped clearly
- did it avoid proposing implementation changes

### Pass 2

- did the agent keep the work docs-only
- does the harness describe the system as it works today
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
- was product behavior preserved
