---
name: submit-for-review
description: "Submit work for peer review. Use when: opening a PR, marking a PR ready for review, moving a ticket to in-review, finishing development on a branch, submitting for code review, requesting review."
---

# Submit for Review

Goal: wrap up development on the current branch — update docs, open (or un-draft) a PR, and move the Jira ticket to In Review.

## Procedure

### 1) Identify the ticket

Extract the Jira ticket key from the current git branch name (e.g. `PLAT-214` from `PLAT-214-robust-cloud-init-error-messages`). If the workspace has multiple repos, check branches across all of them.

If the branch doesn't contain a ticket key (hotfix/experiment), skip the Jira steps.

### 2) Update documentation

Review the diff against the default branch. For each repo with changes, check whether any of these need updating:

- **README.md** files in changed project/module directories — add or revise descriptions of new behavior, dependencies, or gotchas.
- **Agent/AI docs** (AGENTS.md, copilot-instructions.md, skills) — if the changes introduce new workflows, conventions, or terminology that an agent should know about.

Keep updates brief and factual. Don't touch docs that aren't affected by the changes.

### 3) Open or un-draft the pull request

Check whether a PR already exists for the current branch:

- **No PR exists** — Open a new PR against the default branch. Use the ticket summary (or branch description for hotfixes/experiments) as the PR title. Include a concise description of the changes.
- **Draft PR exists** — Mark it as ready for review.
- **PR already open and not draft** — No action needed; note this to the user.

### 4) Transition the Jira ticket

If a ticket key was found in step 1:

1. Fetch available transitions for the ticket using the Atlassian MCP tools.
2. Transition the ticket to **In Review**.

### 5) Summary

Present the user with:
- Documentation files updated (if any)
- PR link and status
- Jira ticket status (if applicable)
