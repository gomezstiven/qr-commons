# QR Commons

Open-source, local-first tooling for generating static QR codes you actually own.

> Static QR codes are a utility, not a subscription.

QR Commons is intended to make standards-correct, portable QR generation freely available without accounts, redirects, tracking, expiring links, or proprietary infrastructure.

## Project status

**Pre-alpha / R0.1 design.** The repository has an accepted R0 project boundary and is now defining the first portable executable milestone. R0.1 establishes the open-source infrastructure and contracts for a deterministic static QR core before building a polished hosted application.

See [R0.1 — Portable Static Core](./docs/milestones/R0.1.md) and the [R0.1 infrastructure architecture](./docs/architecture/R0.1-INFRASTRUCTURE.md).

## Principles

1. **Static means static.** Encoded content must resolve directly to the user-provided payload.
2. **Local-first.** Static generation should not require sending QR contents to a server.
3. **No lock-in.** Exported artifacts remain useful if qr-commons disappears tomorrow.
4. **Correct before decorative.** Scannability, standards compliance, quiet zones, contrast, and print-readiness take priority over styling.
5. **Open core, actually open.** The static authoring tool is not a crippled demo for a paid product.
6. **Generation is not resolution.** Dynamic redirects, analytics, campaign routing, and managed destinations belong to a separate infrastructure layer.

## Intended capabilities

- URL and plain-text QR codes
- Structured payloads such as Wi-Fi, vCard, email, phone, SMS, location, and events
- Deterministic SVG rendering
- PNG export
- Explicit error-correction controls
- Safe logo placement and styling constraints
- Contrast and scannability validation
- Print-oriented sizing and presets
- Batch generation
- Browser-only operation and offline/PWA support
- Reusable packages and, later, a CLI

## Repository shape

```text
qr-commons/
├── apps/
│   └── web/                 # Downstream hosted reference experience
├── packages/
│   ├── core/                # Canonical symbol model + encoding contract
│   ├── formats/             # Reserved until structured payload APIs exist
│   ├── renderer/            # Matrix-to-artifact rendering; SVG first
│   └── validator/           # Reserved until a public preflight API exists
├── tests/
│   └── conformance/         # Cross-package independent checks (R0.1)
├── docs/
│   ├── milestones/
│   ├── decisions/
│   └── architecture/
└── .github/
```

The repository is deliberately separated from any dynamic QR resolver or hosted redirect service.

## License

Apache License 2.0. See [LICENSE](./LICENSE).

## Trademarks

See [TRADEMARKS.md](./TRADEMARKS.md). “QR Code” is a registered trademark of DENSO WAVE INCORPORATED in Japan and other countries. QR Commons is independent and is not affiliated with or endorsed by DENSO WAVE.

## Author

Created by Stiven Gómez Barrientos as an independent open-source project.
