# Contributing

QR Commons is in bootstrap stage. Contributions are welcome, but architecture and public API decisions should stay deliberately small until the core behavior is proven.

## Development baseline

- Node.js 24 LTS is the recommended contributor runtime.
- Node.js 22 and 24 are the R0.1 compatibility targets.
- Use the repository-pinned pnpm version.
- Library code in `packages/core` and `packages/renderer` must remain independent from React, Next.js, browser storage, authentication, analytics, and hosted APIs.

## Principles for contributions

- preserve the distinction between static generation and managed resolution;
- prefer correctness and interoperability over decorative complexity;
- do not introduce required accounts, tracking, redirects, or payload telemetry;
- keep reusable QR logic outside the reference web application;
- include tests with behavioral changes;
- document new dependencies and why they are necessary;
- do not expose third-party implementation APIs as QR Commons public contracts;
- treat prior private/product implementations as behavioral references, not copy sources.

## New dependencies

A pull request that adds a runtime dependency should explain:

1. what behavior it provides;
2. why QR Commons should not implement that behavior itself at this stage;
3. its license;
4. whether it adds network, telemetry, native-runtime, browser, or platform assumptions;
5. how the dependency is isolated from the QR Commons public API;
6. how upgrades will be detected by tests or conformance fixtures.

Dev/test-only dependencies should also be identified when they perform conformance or security-critical validation.

## Workflow

1. Open or select an issue for non-trivial changes.
2. Create a focused branch.
3. Keep commits scoped and explain behavioral changes.
4. Add or update tests.
5. Open a pull request describing scope, trade-offs, and validation performed.

Until a contributor base exists, lightweight maintainer review is preferred over heavyweight governance.
