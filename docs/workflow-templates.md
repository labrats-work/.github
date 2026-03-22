# Workflow Templates

This directory contains GitHub Actions workflow templates available to all repositories in the `labrats-work` organization.

## Available Templates

### repo-info

**File:** `workflow-templates/repo-info.yml`

Prints repository metadata and the full GitHub context at workflow runtime. Useful as a starting point for understanding available context variables or for debugging GitHub Actions workflows.

**Triggers:** Push and pull requests to the default branch

**Steps:**
1. Checkout the repository
2. Print the repository name, workspace disk usage, and full `github` context as JSON

**Usage:** Select "Repo Info Workflow" from the Actions template picker in any org repository.

## Adding a New Template

Each template requires two files in `workflow-templates/`:

1. **`<name>.yml`** — The workflow definition. Use `$default-branch` instead of hardcoded branch names.
2. **`<name>.properties.json`** — Metadata with the following fields:

| Field | Description |
|-------|-------------|
| `name` | Human-readable name shown in the template picker |
| `description` | Short description of what the workflow does |
| `iconName` | GitHub Octicon name (e.g., `check-square`, `rocket`) |
| `categories` | Array of category strings for filtering |
| `filePatterns` | Optional array of file glob patterns that trigger the suggestion |

See [GitHub docs on workflow templates](https://docs.github.com/en/actions/writing-workflows/using-workflow-templates) for full details.
