# labrats-work/.github

Organization-wide GitHub configuration for [labrats-work](https://github.com/labrats-work), including the org profile, reusable workflow templates, and shared GitHub configuration.

## Purpose

This repository serves three roles:

1. **Organization Profile** — `profile/README.md` is displayed on the labrats-work GitHub organization page.
2. **Workflow Templates** — `workflow-templates/` provides starter workflows available to all repositories in the organization.
3. **Org-Wide GitHub Config** — `.github/` holds workflows and settings that apply at the organization level.

## Quick Start

### Using a Workflow Template

1. In any repository under `labrats-work`, go to **Actions → New workflow**.
2. Workflow templates defined in this repo appear under the organization section.
3. Select a template and follow the setup instructions in the generated workflow file.

### Contributing a New Workflow Template

1. Add the workflow YAML to `workflow-templates/<name>.yml`.
2. Add a corresponding `workflow-templates/<name>.properties.json` with `name`, `description`, `iconName`, and `categories`.
3. Open a PR — the template becomes available org-wide once merged to `main`.

## Structure

```
.github/
  workflows/          # Org-level GitHub Actions workflows
profile/
  README.md           # Organization profile shown on GitHub
workflow-templates/
  *.yml               # Reusable workflow templates for the org
  *.properties.json   # Metadata for each workflow template
docs/
  workflow-templates.md   # Guide for workflow templates
  ai-agents.md            # Overview of the org AI agent system
```

## Related

- [labrats-work org profile](https://github.com/labrats-work)
- [actions.common](https://github.com/labrats-work/actions.common) — Reusable GitHub Actions
- [apps.github-ai-agents](https://github.com/labrats-work/apps.github-ai-agents) — AI agent service
