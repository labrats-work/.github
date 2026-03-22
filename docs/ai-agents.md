# AI Agents

The `labrats-work` organization uses a multi-agent AI automation system powered by Claude. Agents handle routine development tasks via GitHub issues and pull requests.

## How It Works

1. A human (or bot) opens or comments on an issue/PR.
2. The agent service (`apps.github-ai-agents`) listens for webhook events.
3. When an agent is triggered (via label or `@mention`), it clones the target repo and executes the task.
4. The agent commits changes, creates a PR, and posts status comments.

## Triggering Agents

### Via Label

Apply a label to an issue or PR to trigger the corresponding agent:

| Label | Agent |
|-------|-------|
| `ai-developer` | `@ai-developer` — implements features/fixes |
| `ai-reviewer` | `@ai-reviewer` — reviews PRs |
| `ai-architect` | `@ai-architect` — designs solutions |
| `ai-docs` | `@ai-docs` — writes documentation |
| `ai-testing` | `@ai-testing` — writes tests |
| `ai-security` | `@ai-security` — security audits |
| `ai-ops` | `@ai-ops` — ops/infra diagnostics |
| `ai-triage` | `@ai-triage` — lightweight issue triage |

### Via Mention

Comment `@ai-developer please ...` (or any agent name) in an issue or PR to delegate a task.

## Agent Roles

### @ai-developer
Implements features, fixes bugs, addresses PR review feedback. Creates branches, commits, opens PRs.

### @ai-reviewer
Reviews pull requests for code quality, correctness, and org standards. Posts review comments.

### @ai-architect
Designs solutions for complex features. Produces implementation plans before dev work begins.

### @ai-docs
Writes and maintains documentation. Reviews existing docs for accuracy.

### @ai-testing
Writes unit, integration, and e2e tests. Improves coverage for existing code.

### @ai-security
Audits code for vulnerabilities. Reviews dependencies, secrets handling, and OWASP concerns.

### @ai-ops
Diagnoses CI failures, infrastructure issues, and deployment problems.

### @ai-triage
Quick issue assessment and labeling. Lightweight analysis to route issues to the right agent.

## Delegation Chain

A typical flow for a new feature:

```
Issue opened
  → @ai-triage (assess complexity)
  → @ai-architect (design if complex)
  → @ai-developer (implement)
  → @ai-reviewer (review)
  → @ai-docs (document)
```

## Infrastructure

The agent service source is at `labrats-work/apps.github-ai-agents`. It uses:
- GitHub App authentication via `GH_TOKEN`
- Claude Sonnet/Haiku models via Anthropic API
- Per-task repo cloning into isolated workspaces
