# QR Commons

**English** · [Español](./README.es.md)

Open-source, local-first, high-reliability tooling for generating static QR codes you actually own.

> Static QR codes are a utility, not a subscription.

QR Commons is intended to make standards-correct, portable QR generation freely available without accounts, proprietary redirects, payload tracking, expiring links, or dependence on QR Commons-controlled infrastructure.

QR generation itself is not novel. Thousands of generators exist. The project's value is to provide a primitive that is **correct, deterministic, portable, auditable, privacy-preserving by architecture, dependency-disciplined, and practical to adopt**.

## Project status

**Pre-alpha / R0.1 design.** The repository has an accepted R0 project boundary and is defining the first portable executable milestone. R0.1 establishes the OSS infrastructure and contracts for a deterministic static QR core before building a polished hosted application.

Start with:

- [R0.1 — Portable Static Core](./docs/milestones/R0.1.md)
- [R0.1 Infrastructure](./docs/architecture/R0.1-INFRASTRUCTURE.md)
- [Public Infrastructure Quality Model](./docs/architecture/PUBLIC-INFRASTRUCTURE.md)
- [Language Policy](./docs/LANGUAGE-POLICY.md)

## Who this should work for

QR Commons is being designed so that it can become useful to:

- an individual using the future free hosted web tool;
- a company embedding generation in internal or customer-facing systems;
- a public institution that needs auditable source and predictable behavior;
- a printer or production workflow generating large numbers of artifacts;
- a developer using libraries or automation;
- a team that prefers self-hosting;
- a downstream product that must not depend on QR Commons servers.

A static artifact exported from QR Commons should remain useful if QR Commons disappears tomorrow, provided the encoded destination itself remains valid.

## Principles

1. **Static means static.** Encoded content resolves directly to the user-provided payload.
2. **Local-first.** Standard static generation should not require sending QR contents to a server.
3. **No lock-in.** Exported artifacts remain useful without QR Commons infrastructure.
4. **Correct before decorative.** Scannability, structure, quiet zones, and conformance take priority over styling.
5. **Deterministic by default.** Identical canonical inputs should produce reproducible canonical outputs within a given release contract.
6. **Dependencies must earn their place.** Runtime dependencies are part of the project's trust surface and should remain deliberately small and replaceable.
7. **Generation is not resolution.** Dynamic redirects, analytics, campaign routing, and managed destinations belong to a separate infrastructure layer.
8. **Usability is infrastructure.** Useful errors, sensible defaults, documentation, compatibility, and migration behavior are part of project quality.

## R0.1 reference pipeline

```text
text payload
    ↓
@qr-commons/core
    ↓
QR Commons symbol / borderless matrix
    ↓
@qr-commons/renderer
    ↓
deterministic SVG
    ↓
independent conformance
```

The canonical matrix does not contain presentation margin. The renderer owns quiet-zone presentation and artifact geometry.

## Intended capabilities

Over time, QR Commons may include:

- URL and plain-text QR codes;
- structured payloads such as Wi-Fi, vCard, email, phone, SMS, location, and events;
- deterministic SVG rendering;
- PNG and print-oriented exports;
- explicit error-correction controls;
- safe logo placement with enforceable protected regions;
- controlled module/finder styling backed by conformance;
- contrast and scannability checks;
- print-oriented sizing and presets;
- batch generation from CSV/JSON;
- offline/PWA support;
- reusable packages and a CLI;
- production preflight tooling.

R0.1 deliberately prefers a small verified core over a large feature list.

## Repository shape

```text
qr-commons/
├── apps/
│   └── web/                 # downstream hosted reference experience
├── packages/
│   ├── core/                # canonical symbol model + encoding contract
│   ├── formats/             # reserved until structured payload APIs exist
│   ├── renderer/            # matrix-to-artifact rendering; SVG first
│   └── validator/           # reserved until a public preflight API exists
├── tests/
│   └── conformance/         # cross-package independent checks (R0.1)
├── docs/
│   ├── milestones/
│   ├── decisions/
│   └── architecture/
└── .github/
```

The repository is deliberately separated from any dynamic QR resolver or hosted redirect service.

## Public-infrastructure quality bar

Reliability, portability, privacy, supply-chain discipline, and operational usability are product features of QR Commons—not release polish.

The project is building toward a simple adoption promise:

> You can audit it, run it locally, embed it, self-host it, automate it, export from it, and leave it — without your static QR codes becoming dependent on us.

See [PUBLIC-INFRASTRUCTURE.md](./docs/architecture/PUBLIC-INFRASTRUCTURE.md).

## Languages

English is the canonical technical language for code, APIs, ADRs, and normative specifications.

Spanish is the first officially maintained translation language. Issues and discussions may be opened in English or Spanish.

See [README.es.md](./README.es.md) and [LANGUAGE-POLICY.md](./docs/LANGUAGE-POLICY.md).

## License

Apache License 2.0. See [LICENSE](./LICENSE).

## Trademarks

See [TRADEMARKS.md](./TRADEMARKS.md). “QR Code” is a registered trademark of DENSO WAVE INCORPORATED in Japan and other countries. QR Commons is independent and is not affiliated with or endorsed by DENSO WAVE.

## Author

Created by Stiven Gómez Barrientos as an independent open-source project.
