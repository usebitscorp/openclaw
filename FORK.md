# @klausai/openclaw fork

This is a maintained fork of [openclaw/openclaw](https://github.com/openclaw/openclaw) published as `@klausai/openclaw` on npm.

## Branch strategy

- `main` — tracks upstream `openclaw/openclaw` (synced via GitHub fork)
- `patches` — our patches rebased on top of a specific upstream release tag

## Updating to a new upstream version

```bash
# In your local clone of this fork
git fetch upstream --tags
git checkout patches
git rebase v2026.X.Y   # the new upstream tag
# Resolve conflicts if any, then:
git push origin patches --force-with-lease

# Tag and push to trigger publish
git tag v2026.X.Y-klausai.1
git push origin v2026.X.Y-klausai.1
```

## Publishing

Push a `v*` tag to the `patches` branch to trigger the publish workflow, or use `workflow_dispatch` from the Actions tab.

Requires `NPM_TOKEN` secret set on the repo (npm automation token for the `@klausai` org).

## Setup requirements

1. **npm org**: `klausai` on npmjs.com (for the `@klausai` scope)
2. **npm token**: Automation token added as `NPM_TOKEN` repo secret
