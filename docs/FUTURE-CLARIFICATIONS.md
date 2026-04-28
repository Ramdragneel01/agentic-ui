# Future Clarifications

This file tracks non-obvious design choices and when to revisit them.

## 2026-04-28

1. Storybook build remains in CI and Pages workflows to guarantee documentation parity with package exports.
2. Release pipeline is tag-driven to prevent accidental npm publishes on branch pushes.
3. Coverage gate currently validates critical component behavior; visual regression snapshots are deferred to a later milestone.

## Planned Follow-ups

1. Add Playwright visual regression tests against Storybook stories.
2. Introduce semantic-release or changesets for automated version bumping.
3. Add design token theming layers for enterprise branding and dark mode.
