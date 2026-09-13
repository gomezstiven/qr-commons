# QR Commons

Open-source, local-first tooling for generating static QR codes you actually own.

> Static QR codes are a utility, not a subscription.

QR Commons is intended to make standards-correct, portable QR generation freely available without accounts, redirects, tracking, expiring links, or proprietary infrastructure.

## Project status

**Pre-alpha / bootstrap.** The repository currently establishes the project contract, architecture boundaries, contribution model, and implementation roadmap. The first implementation milestone will extract and generalize the proven deterministic QR generation work that motivated the project.

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
│   └── web/                 # Hosted free authoring experience
├── packages/
│   ├── core/                # Canonical QR domain model + encoding contracts
│   ├── formats/             # URL/text/Wi-Fi/vCard/etc payload adapters
│   ├── renderer/            # Deterministic SVG/raster rendering contracts
│   └── validator/           # Safety, contrast, sizing and scannability rules
├── docs/
│   ├── PROJECT-CHARTER.md
│   ├── ROADMAP.md
│   └── architecture/
│       └── BASELINE.md
└── .github/                 # Contribution and issue workflow
```

The repository is deliberately separated from any dynamic QR resolver or hosted redirect service.

## License

Apache License 2.0. See [LICENSE](./LICENSE).

## Author

Created by Stiven Gómez Barrientos as an independent open-source project.
