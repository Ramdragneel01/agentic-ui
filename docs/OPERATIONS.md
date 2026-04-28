# Operations Guide

## Runtime Targets

1. npm package consumers import from npm registry.
2. Storybook static docs are hosted on GitHub Pages.

## Health Checklist Per Release

1. CI workflow is green on default branch.
2. Storybook Pages deploy succeeds and pages URL is reachable.
3. npm package publish succeeds for semantic tag.
4. Package install smoke test works in a clean sample app.

## Smoke Commands

```bash
npm ci
npm run typecheck
npm run test:ci
npm run build
npm run build-storybook
```

## Incident Response

1. If npm release fails, verify `NPM_TOKEN` secret and tag format (`vX.Y.Z`).
2. If Pages deploy fails, verify `Settings -> Pages -> Build and deployment -> GitHub Actions`.
3. If build regresses, pin failing dependency in `package.json` and publish patch version.

## Rollback

1. Publish a patch tag for known-good commit.
2. Deprecate bad npm version with:
   `npm deprecate agentic-ui@<bad-version> "Use <good-version> due to regression"`
