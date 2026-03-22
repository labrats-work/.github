# Workflow Templates

This directory documents the reusable workflow templates available to all repositories in the `labrats-work` organization.

## How Templates Work

GitHub surfaces workflow templates from `workflow-templates/` in any repo's **Actions → New workflow** page under the organization section. Each template requires:

1. **`<name>.yml`** — The workflow YAML. Use `$default-branch` as a placeholder for the repo's default branch.
2. **`<name>.properties.json`** — Metadata displayed in the GitHub UI.

### Properties JSON Schema

```json
{
  "name": "Human-readable template name",
  "description": "Short description shown in GitHub UI",
  "iconName": "octicon icon name (e.g. check-square)",
  "categories": ["Text"],
  "filePatterns": ["optional glob patterns that suggest this template"]
}
```

## Available Templates

### `repo-info`

Dumps repository context information (name, workspace size, GitHub context JSON) on push and pull request events.

**Use case:** Debugging, onboarding, verifying runner environments.

**File:** `workflow-templates/repo-info.yml`

## Adding a New Template

1. Create `workflow-templates/<name>.yml` with your workflow.
2. Create `workflow-templates/<name>.properties.json` with metadata.
3. Open a PR against `main`.
4. Once merged, the template is immediately available org-wide.

## References

- [GitHub Docs — Creating workflow templates](https://docs.github.com/en/actions/using-workflows/creating-starter-workflows-for-your-organization)
