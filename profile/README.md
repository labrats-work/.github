# labrats.work

Self-hosted platform and applications, run from Warsaw 🇵🇱 — bare metal, Kubernetes, GitOps, and AI agents that work the backlog alongside humans.

## How it's built

Every repo belongs to one layer, and its name says which ([ADR-0002](https://github.com/labrats-work/standards/blob/main/workspace/docs/adr/0002-repository-naming-convention.md)):

| Layer | Prefix | What lives there | Examples |
|-------|--------|------------------|----------|
| 4 · Apps | `apps.*` | User-facing services | `apps.ai-agents`, `apps.my-budget`, `apps.my-diet`, `apps.life-systems` |
| 3 · Platform | `platform.*` | Per-app deployment slices | `platform.shared` |
| 2 · Runtime | `runtime.*` | Shared cluster substrate | `runtime.k8s.bor`, `runtime.k8s.bor.gitops` |
| 1 · Infra | `infra.*` | Hardware, network, hosts | `infra.bor`, `infra.gx10`, `infra.nas-n5-pro` |
| Support | `actions.*` `modules.*` `docs.*` | Shared CI, IaC modules, records | `actions.common`, `modules.terraform`, `docs.org` |

## Stack

| Area | Technologies |
|------|--------------|
| **Compute** | Proxmox VE, kubeadm Kubernetes, Cilium, NVIDIA GX10 for local inference |
| **Delivery** | Argo CD GitOps, GitHub Actions on self-hosted ARC runners, images on `ghcr.io/labrats-work` |
| **Platform** | Traefik, cert-manager, External Secrets + SOPS/age, Authelia + lldap SSO |
| **Observability** | Prometheus, Grafana, Loki |
| **IaC** | Terraform, Ansible |
| **Apps** | TypeScript (Next.js, Node.js), Go, Python, .NET · PostgreSQL, MongoDB, Redis |
| **AI** | `apps.ai-agents` — agent job runner used for PR review, issue work, and triage; vLLM on GX10 |

## Ways of working

- **Git is the source of truth** — clusters converge on what is merged, never on hand edits.
- **Every PR traces to a Feature** — org rulesets require a linked Task/Bug, a secret scan, conventional titles, and a size check.
- **Decisions are written down** — ADRs, reference architectures (RADs), system designs (SADs), and specs before code.
- **Hardened by default** — non-root containers, read-only filesystems, encrypted secrets, pinned image versions.

## Start here

- 📖 **[docs.org](https://github.com/labrats-work/docs.org)** — the authoritative record of how the org is built and governed.
- 📐 **[standards](https://github.com/labrats-work/standards)** — naming, commits, PR rules, and workspace conventions.

<sub>Most repositories are private; the links above need org membership.</sub>
