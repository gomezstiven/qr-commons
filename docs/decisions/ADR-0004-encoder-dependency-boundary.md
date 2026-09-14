# ADR-0004 — Encoder dependency boundary

Status: **PROPOSED**  
Date: **2026-09-14**

## Context

A prior implementation used the `qr` package to obtain a raw module matrix and then removed the dependency-owned border so rendering could own the quiet zone. That behavior is useful, but QR Commons should not copy the surrounding implementation or expose a third-party library as its public API.

As of this decision, `qr` 0.7.0 is a current, zero-runtime-dependency package distributed under MIT OR Apache-2.0. It supports raw encoding and is suitable as a small reference encoder dependency.

A separate decoder is desirable for conformance tests so QR Commons does not validate encoding solely with the same implementation that produced it.

## Decision

### Default runtime encoder

R0.1 may use `qr` 0.7.x as the default encoder implementation under these constraints:

- it is an implementation detail of `packages/core`;
- QR Commons does not re-export `qr` types or functions;
- QR Commons owns its error-correction vocabulary and input contract;
- QR Commons converts dependency output into its own immutable borderless matrix/symbol representation;
- quiet-zone ownership remains outside the encoder;
- replacing the dependency must not require a consumer API change if QR Commons behavior remains equivalent.

The dependency should be pinned deliberately during R0.1 rather than accepted through a wide floating range.

### Independent conformance decoder

R0.1 should use a decoder from a different implementation lineage for test-only roundtrip checks.

`jsqr` is acceptable as a **test-only** candidate because it is a standalone decoder, has no runtime dependencies, and is Apache-2.0 licensed. Its low maintenance velocity is acceptable for this narrow conformance role but is a reason not to make it part of QR Commons runtime behavior.

The conformance decoder must never ship as a required runtime dependency of `core` or `renderer`.

### No vendored encoder algorithm in R0.1

QR Commons will not copy or fork an encoder implementation into its own source tree during R0.1.

Owning the authoring contract does not require owning Reed-Solomon, masking, mode selection, and bit-placement implementation immediately. A future decision may revisit this if auditability, performance, standards coverage, or maintenance justify it.

## Consequences

### Positive

- minimal runtime dependency surface;
- clear replacement boundary;
- no accidental third-party API lock-in;
- independent semantic roundtrip verification;
- avoids spending R0.1 rebuilding a standards encoder without product value.

### Risks

- QR Commons initially depends on third-party encoding correctness;
- behavior changes in the encoder package must be detected by fixtures/conformance tests;
- dependency upgrades require review rather than automatic trust.

## Upgrade policy

A runtime encoder upgrade must pass:

1. deterministic fixture comparison or an explicitly reviewed fixture migration;
2. matrix dimension invariants;
3. independent decode roundtrip coverage;
4. browser and supported Node compatibility;
5. license review;
6. no new network, telemetry, or hosted-service requirement.

## Rejected alternatives

### Copy the previous encoder wrapper verbatim
Rejected because R0.1 is a public re-derivation, not a source migration.

### Use the encoder's own decoder as the only roundtrip test
Rejected because it can reproduce the same implementation defect on both sides.

### Use a styling library as the encoder abstraction
Rejected because it collapses encoding, presentation, and often browser-specific concerns into one dependency boundary.
