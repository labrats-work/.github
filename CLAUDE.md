# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

The `.github` special repository for the `labrats-work` org. Controls the org profile, workflow templates, and org-level automation.

- `profile/README.md` — shown at github.com/labrats-work; keep accurate
- `workflow-templates/` — each template YAML must have a matching `.properties.json`
- `.github/workflows/` — org-level automation

## AI Agent System

The org uses a multi-agent GitHub automation system. Agents are triggered by labels or `@mention` in issue/PR comments:

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

Agent service hosted in `apps.github-ai-agents`.

Workflow template `$default-branch` placeholder is replaced by GitHub when applied.
