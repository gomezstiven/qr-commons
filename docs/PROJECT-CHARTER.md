# QR Commons — Project Charter

Status: **BOOTSTRAP**  
Version: **0.1**  
Date: **2026-09-13**

## 1. Purpose

QR Commons provides a high-quality open-source toolkit for authoring static QR codes without requiring accounts, hosted redirects, tracking infrastructure, subscriptions, or vendor-owned destinations.

The project treats static QR generation as a commodity utility that should remain portable and user-owned.

## 2. Core thesis

**Static QR codes are a utility, not a subscription.**

The project may be used by individuals, companies, public institutions, printers, developers, and other software without dependence on a QR Commons service.

## 3. Constitutional guarantees

### 3.1 Direct payload ownership
A static QR produced by QR Commons encodes the payload selected by the user. QR Commons must not silently substitute a proprietary redirect, tracking URL, shortlink, or controlled destination.

### 3.2 Local-first generation
The canonical web experience should be capable of generating static QRs in the client. Payload contents should not need to leave the user's device for standard generation.

### 3.3 Export portability
SVG, PNG, and future supported formats must remain ordinary, portable artifacts. Export must not depend on QR Commons remaining online.

### 3.4 Correctness before styling
Styling features must be constrained by scannability requirements. The application should warn or prevent unsafe compositions rather than optimize only for appearance.

### 3.5 No artificial feature hostage
Core static QR authoring, export, and standards-correct customization should not be intentionally degraded to manufacture a subscription boundary.

## 4. Scope

QR Commons owns the authoring pipeline:

`payload -> normalize -> encode -> render -> validate -> export`

It may include reusable libraries, a hosted browser application, batch utilities, and a CLI.

## 5. Explicit non-goals

The project does **not** own:

- managed dynamic redirects;
- destination mutation after printing;
- scan analytics or telemetry platforms;
- campaign management;
- user accounts or team billing;
- custom-domain redirect hosting;
- managed QR lifecycle infrastructure;
- proprietary physical-to-digital registries.

Those capabilities may exist in other products, including commercial products, but must remain architecturally separate from the QR Commons static authoring contract.

## 6. Independence

QR Commons is an independent project under the author's personal GitHub identity. It is not an Evenn-branded product and should not depend on Evenn infrastructure to function.

Implementations originally developed in other environments may be contributed only when ownership and licensing allow it and after removing organization-specific assumptions.

## 7. Success criteria

QR Commons succeeds when a user can generate a correct, high-quality static QR, export it, print or distribute it, and continue using that artifact indefinitely without QR Commons being involved again.
