---
name: github-actions-cicd
description: >-
  Senior DevOps practices for CI/CD on GitHub using GitHub Actions: workflows,
  reusable workflows, environments, caching, security, and release hygiene. Use
  when creating or changing workflows, CI pipelines, deployment automation,
  GitHub Environments, secrets, runners, or when the user mentions GitHub
  Actions, CI, CD, pipelines, or .github/workflows.
---

# GitHub Actions — CI/CD (senior DevOps)

## When to apply

Use for **all** CI/CD design and changes in this repo: new pipelines, edits to existing workflows, deployment gates, release automation, and related GitHub configuration (`environments`, `secrets`, `variables`, branch protection alignment).

## Principles

- **Small, fast feedback**: Default branch checks should stay quick; use caching and split heavy jobs sensibly.
- **Least privilege**: Grant workflows only the permissions they need (`permissions:` key); prefer narrowly scoped tokens.
- **Reproducible**: Pin third-party actions to full commit SHAs (or trusted version tags with a conscious exception policy). Pin tool versions (Node, pnpm/npm/yarn, etc.) explicitly in CI.
- **Observable**: Name jobs/steps clearly; surface test/lint/typecheck failures without burying logs; use workflow annotations when useful.
- **Safe secrets**: Never echo secrets; use GitHub Secrets / Environments; prefer **OIDC** to long-lived cloud credentials when deploying to AWS/Azure/GCP.

## Workflow structure (defaults)

- **Triggers**: `on:` — prefer precise paths/filters (`paths`, `paths-ignore`) when workflows should not run on unrelated changes.
- **Concurrency**: Use `concurrency:` to cancel superseded runs on the same branch/PR when safe (avoid for deployment workflows that must complete).
- **Jobs**: One concern per job when parallelism helps; use `needs:` for ordering.
- **Matrix**: Use `strategy.matrix` for cross-version or cross-platform checks; keep matrices minimal to control minutes.
- **Caching**: Cache dependency stores (e.g. pnpm store, npm cache) with stable keys; restore keys for partial hits.

## CI vs CD

- **CI** (merge gates): install deps, lint, typecheck, unit tests, build; optional bundle analysis on schedule or main.
- **CD** (delivery): separate workflow or job with environment protection (`environment:`), manual approval if required, and deployment-specific secrets. Do not run unreviewed deploys from fork PRs.

## Security checklist

- [ ] `permissions:` set explicitly (often `contents: read` for CI; tighter by default).
- [ ] No secrets in logs; mask outputs; avoid `set -x` with sensitive env.
- [ ] Third-party actions pinned (SHA preferred).
- [ ] Fork PRs: restrict `pull_request_target` usage; never run untrusted code with write tokens without hardening.
- [ ] Dependabot or Renovate considered for actions and base images (if Docker used).

## GitHub features to prefer

- **Environments** for staging/production with protection rules and optional reviewers.
- **Reusable workflows** (`workflow_call`) when multiple callers share the same pipeline.
- **Artifacts** for build outputs between jobs when needed; define retention.
- **OIDC** for cloud deploy roles instead of static keys when applicable.

## YAML hygiene

- Validate workflow YAML mentally: correct indentation, `runs-on` appropriate for the stack (`ubuntu-latest` unless Windows/macOS needed).
- Use consistent Node/package manager setup (e.g. `actions/setup-node` with cache option matching the package manager).
- Document non-obvious choices in short comments above the relevant `job` or `step` (not essays).

## Additional reference

For patterns and troubleshooting notes, see [reference.md](reference.md).
