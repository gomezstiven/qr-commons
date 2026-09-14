# Contributing

**English** · [Español](./CONTRIBUTING.es.md)

QR Commons is in pre-alpha. Contributions are welcome, but architecture and public API decisions should stay deliberately small until the core behavior is proven.

Code, identifiers, commit messages, and normative technical artifacts remain in English. Issues and design discussion may be written in English or Spanish.

## Development baseline

- Node.js 24 LTS is the recommended contributor runtime.
- Node.js 22 and 24 are the R0.1 compatibility targets.
- Use the repository-pinned pnpm version.
- Library code in `packages/core` and `packages/renderer` must remain independent from React, Next.js, browser storage, authentication, analytics, and hosted APIs.

## Principles for contributions

- preserve the distinction between static generation and managed resolution;
- prefer correctness, interoperability, and portability over decorative complexity;
- do not introduce required accounts, tracking, redirects, or payload telemetry for static generation;
- keep reusable QR logic outside the reference web application;
- include tests or fixtures with behavioral changes;
- document new dependencies and why they are necessary;
- do not expose third-party implementation APIs as QR Commons public contracts;
- treat prior private/product implementations as behavioral references, not copy sources;
- avoid expanding public APIs before real usage and conformance evidence justify them;
- prefer small, reviewable, reversible changes.

## New dependencies

A runtime dependency becomes part of QR Commons' trust and supply-chain surface.

A pull request that adds one should explain:

1. what behavior it provides;
2. why QR Commons should not implement that behavior itself at this stage;
3. its license and compatibility with Apache-2.0;
4. transitive dependency footprint;
5. whether it adds network, telemetry, native-runtime, browser, or platform assumptions;
6. bundle/runtime impact where relevant;
7. how it is isolated from the QR Commons public API;
8. how upgrades will be detected by tests or conformance fixtures.

Dev/test-only dependencies may be broader when they improve independent conformance or security validation, but they must not leak into production bundles.

## Public APIs

An exported function is not automatically a stable public API.

Before stable releases, package contracts may change while behavior is being proven. New abstractions should be backed by real behavior rather than speculative package structure.

Durable architecture, compatibility, licensing, or project-boundary decisions may require an ADR.

## Workflow

1. Open or select an issue for non-trivial changes.
2. Explain the problem and smallest useful capability.
3. Create a focused branch.
4. Keep commits scoped and explain behavioral changes.
5. Add or update tests and fixtures.
6. Open a pull request describing scope, trade-offs, dependencies, and validation performed.

## Languages

English is the canonical technical language. Spanish is the first officially maintained translation language.

An actionable contribution written in Spanish should not be rejected merely because it was not initially translated. Maintainers may add an English technical summary when useful for broader review.

See [docs/LANGUAGE-POLICY.md](./docs/LANGUAGE-POLICY.md).

## Governance

QR Commons is currently maintainer-led. Durable architecture decisions are recorded through ADRs and significant changes are reviewed publicly through issues and pull requests whenever possible.

See [GOVERNANCE.md](./GOVERNANCE.md).

## Security

Do not disclose security-sensitive issues publicly when doing so could expose users or downstream consumers. See [SECURITY.md](./SECURITY.md).
