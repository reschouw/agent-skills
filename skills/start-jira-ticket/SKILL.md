---
name: start-jira-ticket
description: "Start work on a Jira ticket, hotfix, or experiment. Use when: beginning a new task, starting a ticket, creating a branch for a PLAT ticket, kicking off work from a Jira issue number, starting a hotfix, beginning an experiment or investigation branch."
---

# Start Work

Goal: set up the working branch (and optionally pull a Jira ticket into context) so the user can plan next steps.

## Branch types

Determine the branch type from the user's request:

| Type | Has Jira ticket? | Branch prefix | Example |
|------|-------------------|---------------|---------|
| **Ticket** | Yes | `<TICKET-NUMBER>-` | `PLAT-214-robust-cloud-init-error-messages` |
| **Hotfix** | No | `hotfix-` | `hotfix-thing-is-broken` |
| **Experiment** | No | `experiment-` | `experiment-test-new-vpc-layout` |

- The suffix is always 2–4 lowercase words separated by hyphens describing the work.
- For ticket branches, derive the description from the ticket summary.
- For hotfix/experiment branches, derive it from the user's description of the work.

## Procedure

### 1) Create a branch

1. Ensure you are on the default branch and it is up to date (`git checkout master && git pull`).
2. Create and switch to the new branch: `git checkout -b <branch-name>`.

### 2) If a Jira ticket was provided

a. **Fetch the ticket** — Use the Atlassian MCP tools to retrieve the ticket summary, description, acceptance criteria, and current status.

b. **Transition the ticket** — Move the Jira ticket to **In Progress** using the Atlassian MCP transition tool (find the correct transition ID from the available transitions first).

c. **Summarize and hand off to planning** — Present the user with:
   - **Ticket**: key, summary, and status
   - **Branch**: the newly created branch name
   - **Description / Acceptance Criteria**: the relevant details from the ticket

   Then ask the user if they'd like to switch to planning mode to break the work into steps.

### 3) If no Jira ticket (hotfix / experiment)

Present the user with:
- **Branch**: the newly created branch name
- **Purpose**: brief restatement of what the branch is for

Then ask the user how they'd like to proceed.
