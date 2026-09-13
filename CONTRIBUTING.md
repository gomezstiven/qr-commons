# Contributing

QR Commons is in bootstrap stage. Contributions are welcome, but architecture and public API decisions should stay deliberately small until the core behavior is proven.

## Principles for contributions

- preserve the distinction between static generation and managed resolution;
- prefer correctness and interoperability over decorative complexity;
- do not introduce required accounts, tracking, redirects, or payload telemetry;
- keep reusable QR logic outside the reference web application;
- include tests with behavioral changes;
- document new dependencies and why they are necessary.

## Workflow

1. Open or select an issue for non-trivial changes.
2. Create a focused branch.
3. Keep commits scoped and explain behavioral changes.
4. Add or update tests.
5. Open a pull request describing scope, trade-offs, and validation performed.

Until a contributor base exists, lightweight maintainer review is preferred over heavyweight governance.
