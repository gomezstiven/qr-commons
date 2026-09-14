# Roadmap

The roadmap is directional, not a release promise.

## R0.1 — Portable static core

- public OSS runtime/tooling baseline;
- canonical text payload and error-correction contract;
- immutable borderless QR matrix/symbol model;
- default encoder isolated behind QR Commons-owned APIs;
- deterministic SVG renderer with standards-safe quiet zone;
- independent conformance roundtrip tests;
- Node/browser-compatible library boundaries;
- no npm publication yet.

**Exit condition:** the repository can turn representative text payloads into deterministic, standards-correct SVG artifacts and independently verify semantic roundtrip without accounts, redirects, server-side payload processing, UI framework dependencies, or organization-specific infrastructure.

## v0.1 — Correct static utility

- URL-oriented authoring on top of the R0.1 text core;
- browser reference experience;
- baseline user-facing validation;
- SVG export workflow;
- first public package/release decision if contracts have proven stable.

**Exit condition:** QR Commons can replace a basic static QR generator without accounts, redirects, or server-side payload processing.

## v0.2 — Practical authoring

- Wi-Fi, email, phone, SMS, vCard formats;
- PNG export;
- reusable presets;
- improved validation messages;
- print-size guidance.

## v0.3 — Safe customization

- foreground/background controls;
- module and finder styling;
- logo placement with enforced safe area;
- contrast checks;
- visual regression coverage.

## v0.4 — Scale and portability

- batch generation from CSV/JSON;
- offline/PWA support;
- local presets/history;
- improved accessibility;
- import/export of authoring configuration.

## v1.0 — Stable public utility

- documented stable contracts;
- hardened browser compatibility;
- CLI decision and, if retained, stable CLI;
- package publication strategy;
- security and privacy review;
- contributor documentation matured from real project usage.
