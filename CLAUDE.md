# CLAUDE.md

This file provides context for AI agents (Claude Code) working in this repository.

## Repository Purpose

This is the `labrats-work/.github` special repository. It contains:
- Organization profile README (`profile/README.md`)
- Reusable workflow templates (`workflow-templates/`)
- Workflows for CI on this repository itself (`.github/workflows/`)

## Key Files

| File | Purpose |
|------|---------|
| `profile/README.md` | Org profile shown at github.com/labrats-work — keep it current with active projects and tech stack |
| `workflow-templates/repo-info.yml` | Example workflow template demonstrating repo info output |
| `workflow-templates/repo-info.properties.json` | Metadata for the repo-info template |
| `.github/workflows/repo-info.yml` | CI workflow for this repository (runs on push/PR to main) |

## Conventions

- Workflow templates must have a matching `.properties.json` file
- The `properties.json` `iconName` must reference a valid GitHub icon
- Templates use `$default-branch` as a placeholder; the live workflow pins to `main`
- Commit messages follow conventional commits: `feat:`, `fix:`, `docs:`, `chore:`

## Agent Roles

This repository uses the `labrats-work` multi-agent system. Agents are triggered by GitHub issue labels:
- `ai-developer` — implements changes, creates PRs
- `ai-reviewer` — reviews PRs
- `ai-docs` — documentation reviews and improvements

See the [agent directory](https://github.com/labrats-work/.github/blob/main/profile/README.md) for the full list.
