# Architecture Baseline

Status: **R0**

## 1. Boundary

QR Commons is an authoring system, not a resolution service.

```text
AUTHORING (QR Commons)
input
  -> payload adapter
  -> canonical payload
  -> encoder
  -> matrix
  -> renderer
  -> validator
  -> export

RESOLUTION (out of scope)
scan
  -> encoded destination
  -> destination infrastructure controlled by the QR owner
```

## 2. Monorepo baseline

### `packages/core`
Framework-independent domain primitives.

Responsibilities:
- canonical QR input/output types;
- encoding configuration;
- error-correction model;
- matrix abstraction;
- deterministic serialization contracts;
- capability interfaces used by other packages.

Must not depend on React, Next.js, browser storage, analytics, or a hosted API.

### `packages/formats`
Structured payload adapters.

Initial targets:
- text;
- URL;
- Wi-Fi;
- email;
- phone;
- SMS;
- vCard.

Adapters convert user-friendly structured input into canonical QR payload strings. They do not own rendering.

### `packages/renderer`
Matrix-to-artifact rendering.

Initial target:
- deterministic SVG.

Later targets:
- raster/PNG;
- print-oriented output helpers.

Renderer owns geometry and styling constraints, not payload semantics.

### `packages/validator`
Cross-cutting quality rules.

Initial rules:
- quiet-zone checks;
- minimum contrast guidance;
- logo safe-area constraints;
- dimensions and module-size warnings;
- configuration sanity checks.

Later versions may add decode-roundtrip verification using an independent decoder.

### `apps/web`
Reference user experience and hosted free tool.

Requirements:
- local-first static generation;
- no account required for standard use;
- no payload telemetry by default;
- export from the browser;
- responsive and accessible;
- eventually installable/offline as a PWA.

The web app composes packages; it should not become the source of truth for QR logic.

## 3. Technology baseline

Proposed:
- TypeScript;
- pnpm workspaces;
- browser-first packages with explicit Node compatibility where practical;
- Next.js for the reference web application only;
- deterministic SVG as the canonical vector output;
- Vitest for package-level tests;
- Playwright for browser/export acceptance once the web app exists.

No implementation dependency is constitutional. Package boundaries and behavioral contracts matter more than a specific framework.

## 4. Quality gates

Before v1.0, the project should demonstrate:

1. deterministic output for identical canonical inputs;
2. encode/decode roundtrip coverage across representative payloads;
3. export integrity for SVG and PNG;
4. accessibility checks for the authoring UI;
5. browser compatibility across current major engines;
6. documented print-sizing guidance;
7. no required network request containing QR payload content during static generation;
8. stable public package contracts or an explicit declaration that packages are internal-only.

## 5. Extraction rule

Existing QR code from other projects should not be copied wholesale. Extraction should proceed capability-by-capability:

1. identify reusable primitive;
2. remove product-specific routing, branding, tracking, and configuration;
3. establish tests around behavior;
4. move into the appropriate package;
5. preserve provenance in commit/PR documentation when relevant.
