# labrats-work/.github

Organization-wide GitHub configuration repository for [labrats-work](https://github.com/labrats-work).

## Purpose

This repository provides default community health files and shared configurations for all repositories in the `labrats-work` organization. Files placed here are automatically used by repositories that do not have their own versions.

Contents:
- **Organization profile** — The public-facing README shown on the organization's GitHub page
- **Workflow templates** — Reusable GitHub Actions workflow templates available to all org repositories
- **Community health files** — Default CONTRIBUTING, CODE_OF_CONDUCT, SECURITY, and SUPPORT documents (when present)

## Structure

```
.github/
  workflows/          # Workflows for this repository itself
profile/
  README.md           # Organization profile shown at github.com/labrats-work
workflow-templates/
  *.yml               # Workflow templates available to all org repositories
  *.properties.json   # Metadata for each workflow template
docs/
  workflow-templates.md  # Documentation for available workflow templates
```

## Quick Start

### Using a Workflow Template

1. In any `labrats-work` repository, go to **Actions** > **New workflow**
2. Select a template from the **labrats-work** section
3. Customize the template for your repository's needs

### Adding a New Workflow Template

1. Add a `<name>.yml` file to `workflow-templates/`
2. Add a matching `<name>.properties.json` with `name`, `description`, `iconName`, and `categories`
3. Open a PR — templates are available to the org once merged to `main`

## Related Repositories

- [actions.common](https://github.com/labrats-work/actions.common) — Reusable GitHub Actions workflows
- [apps.github-ai-agents](https://github.com/labrats-work/apps.github-ai-agents) — AI automation service powering this org's agents
