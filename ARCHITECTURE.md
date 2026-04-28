# agentic-ui Architecture

## 1. Package Shape

Single package TypeScript component library with:

1. Source components under `src/components`
2. Public exports from `src/index.ts`
3. Shared styles under `src/styles`
4. Storybook for docs and interaction testing

## 2. Build and Distribution

1. tsup builds ESM and CJS bundles.
2. Type declarations are generated for all public exports.
3. React and ReactDOM remain peer dependencies for consumer compatibility.

## 3. UI Principles

1. Accessibility first: keyboard support, semantic structure, visible focus.
2. Predictable data contracts: explicit typed props.
3. Runtime efficiency: lightweight rendering, no heavy runtime dependencies.

## 4. Deployment Model

1. npm package release on semantic tags.
2. Storybook static build published via GitHub Pages.
3. CI gates: typecheck, package build, Storybook build.

## 5. Security and Quality

1. No eval or dynamic script execution.
2. Controlled rendering of text-only content.
3. Strict TypeScript settings to reduce runtime faults.
