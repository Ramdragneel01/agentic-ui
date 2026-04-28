# Deployment Guide

## Prerequisites

1. Node.js 20 or newer.
2. npm account with publish access for `agentic-ui`.
3. GitHub repository with Actions enabled.

## Repository Configuration

1. Add secret `NPM_TOKEN` in GitHub repository settings.
2. Set Pages source to `GitHub Actions`.
3. Keep default branch protected with required CI status checks.

## Package Build

```bash
npm install
npm run typecheck
npm run test:ci
npm run build
```

Output artifacts:
- `dist/index.js` (ESM)
- `dist/index.cjs` (CJS)
- `dist/index.d.ts` (types)
- `dist/styles.css` (styles)

## npm Publishing

Release workflow publishes on semantic tags.

Required secret:
- `NPM_TOKEN`

Tag flow:

```bash
git tag v0.1.0
git push origin v0.1.0
```

Release workflow file:
- `.github/workflows/release.yml`

## Storybook Deployment

GitHub Pages workflow builds and deploys Storybook static output.

Published output path:
- `storybook-static`

Pages workflow file:
- `.github/workflows/pages.yml`

After first deployment, docs are served at:
- `https://<github-username>.github.io/<repository-name>/`

## CI Validation

CI workflow file:
- `.github/workflows/ci.yml`

CI gates run:
1. `npm run typecheck`
2. `npm run test:ci`
3. `npm run build`
4. `npm run build-storybook`

## Consumer Usage

```tsx
import { StreamingMessage } from "agentic-ui";
import "agentic-ui/styles.css";
```
