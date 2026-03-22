# CLAUDE.md — labrats-work/.github

This file provides context for AI agents (Claude Code and others) working in this repository.

## Repository Purpose

This is the `.github` special repository for the `labrats-work` GitHub organization. It controls:

- **Organization profile** (`profile/README.md`) — shown at github.com/labrats-work
- **Workflow templates** (`workflow-templates/`) — starter workflows surfaced in all org repos
- **Org-level workflows** (`.github/workflows/`) — automation running at org scope

## Key Files

| Path | Purpose |
|------|---------|
| `profile/README.md` | Org profile displayed on GitHub — keep accurate and up to date |
| `workflow-templates/*.yml` | Workflow templates — each must have a matching `.properties.json` |
| `workflow-templates/*.properties.json` | Template metadata: `name`, `description`, `iconName`, `categories` |
| `.github/workflows/repo-info.yml` | Example org workflow (repo info dump) |

## Conventions

- Workflow template YAMLs use `$default-branch` as a placeholder (replaced by GitHub when applied).
- The corresponding `.properties.json` must match the template filename (without extension).
- Keep `profile/README.md` reflecting the actual org tech stack and projects.

## AI Agent System

This org uses multi-agent GitHub automation. Agents are triggered via issue/PR labels and `@mention` in comments:

| Agent | Trigger | Role |
|-------|---------|------|
| `@ai-developer` | `ai-developer` label | Implements features and fixes |
| `@ai-reviewer` | `ai-reviewer` label | Reviews PRs |
| `@ai-architect` | `ai-architect` label | Designs solutions |
| `@ai-docs` | `ai-docs` label | Writes/maintains documentation |
| `@ai-testing` | `ai-testing` label | Writes tests |
| `@ai-security` | `ai-security` label | Security audits |
| `@ai-ops` | `ai-ops` label | Diagnoses failures |
| `@ai-triage` | `ai-triage` label | Quick issue triage |

The agent service is hosted in `apps.github-ai-agents`.

## Branch Naming

Use `feat/`, `fix/`, `docs/`, `chore/`, `refactor/`, `test/` prefixes.

## Commit Style

Follow conventional commits: `type(scope): description` (imperative, under 72 chars).
