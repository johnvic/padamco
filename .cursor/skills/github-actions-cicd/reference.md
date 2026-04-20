# GitHub Actions — extended reference

## Common `permissions` starting point (CI only)

```yaml
permissions:
  contents: read
```

Add `pull-requests: read` or `write` only when a step requires it (e.g. some bots, comment workflows).

## Concurrency example (feature branches / PRs)

```yaml
concurrency:
  group: ${{ github.workflow }}-${{ github.ref }}
  cancel-in-progress: true
```

Skip `cancel-in-progress` for production deploy workflows if in-flight deploys must finish.

## Pinning actions

Prefer full commit SHA:

```yaml
uses: actions/checkout@<full-sha>
```

Document the chosen version in a one-line comment if the team uses tags for readability elsewhere.

## OIDC (directional)

For AWS, Azure, or GCP deploys from Actions, prefer workload identity federation / OIDC over storing long-lived API keys in secrets. Implementation is cloud-specific—follow current provider docs when adding deploy jobs.

## Troubleshooting mindset

- Reproduce locally: same Node version, same install command, same test command.
- Inspect the **Annotations** tab and step logs; upload artifacts on failure for flaky UI/e2e when justified.
