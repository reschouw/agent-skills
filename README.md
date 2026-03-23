# Agent Skills

Source-controlled collection of reusable AI agent skills, intended to be shared across all repos, projects, and workspaces.

## Setup

Clone this repo as `.agents` in your home directory:

```sh
git clone git@github.com:reschouw/agent-skills.git ~/.agents
```

AI tools (e.g. GitHub Copilot, VS Code agents) automatically pick up the `~/.agents` directory, making these skills available in every workspace without per-repo configuration.

## Structure

```
skills/
  start-jira-ticket/SKILL.md   # Branch creation + Jira ticket intake
  submit-for-review/SKILL.md   # PR submission + Jira transition to In Review
```

Each skill is a standalone Markdown file with YAML frontmatter (`name`, `description`) and a documented procedure that an AI agent follows when the skill is triggered.

## Skills

| Skill | Description |
|-------|-------------|
| **start-jira-ticket** | Creates a working branch (ticket, hotfix, or experiment), fetches Jira context, and transitions the ticket to In Progress. |
| **submit-for-review** | Updates docs, opens or un-drafts a PR, and transitions the Jira ticket to In Review. |

## Adding a Skill

1. Create a new directory under `skills/` with a descriptive name.
2. Add a `SKILL.md` file with YAML frontmatter (`name` and `description`) followed by the skill's procedure.
3. Commit and push — the skill will be available in all workspaces on next pull.
