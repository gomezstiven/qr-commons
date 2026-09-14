# QR Commons — Public Infrastructure Quality Model

Status: **PROPOSED for R0.1**  
Scope: repository-wide

QR Commons is not differentiated by the existence of QR generation. QR generators are abundant. The project is differentiated by the quality of the primitive it provides and by the confidence with which an individual, company, institution, public body, printer, developer, or downstream product can depend on it.

The project therefore treats **reliability, portability, privacy, interoperability, maintainability, and operational usability as product features**.

## 1. Public-infrastructure posture

QR Commons should remain useful in all of these scenarios:

- a person uses the hosted web tool once and never returns;
- a company self-hosts the web application;
- an internal engineering team consumes the libraries directly;
- a public institution audits the source before adoption;
- a printer or production workflow produces thousands of static artifacts;
- a downstream product embeds QR generation without depending on QR Commons infrastructure;
- the original hosted service disappears entirely.

The exported QR artifact must continue to work in every scenario where the encoded destination itself remains valid.

## 2. Quality properties

### 2.1 Correctness

A generated symbol must encode exactly the intended canonical payload and satisfy the structural invariants expected of the QR symbol produced by the selected encoding configuration.

Correctness takes precedence over customization.

Required direction:

- explicit error-correction configuration;
- validated matrix dimensions and version derivation;
- independent encode/decode conformance tests;
- standards-safe quiet-zone behavior;
- failures are explicit rather than silently repaired into a different payload.

### 2.2 Determinism

For a fixed QR Commons version, identical canonical input and configuration should produce identical canonical output unless a documented algorithm change intentionally changes that contract.

Determinism supports:

- reproducible tests;
- stable build pipelines;
- content-addressable storage and caching;
- auditability;
- regression detection;
- predictable batch production.

### 2.3 Portability

The reusable core must not require:

- a QR Commons account;
- a QR Commons API;
- a network connection;
- browser storage;
- React, Next.js, or a UI framework;
- a QR Commons-controlled destination.

The canonical matrix and SVG paths should be usable in browser and Node-compatible environments.

### 2.4 Privacy by architecture

Static payload generation must not require payload telemetry.

For the reference web application:

- standard static generation should be local to the client;
- no QR payload should be transmitted merely to encode, render, validate, or export it;
- optional future services that require transmission must be explicit and architecturally separate;
- analytics, if ever present on a hosted surface, must not redefine the library contract or silently capture QR contents.

### 2.5 Dependency discipline

Every runtime dependency is part of the project's trust and supply-chain surface.

A new dependency should be accepted only when it is materially better than owning the required behavior and should be evaluated for:

- necessity;
- license compatibility;
- maintenance activity and release history;
- transitive dependency footprint;
- runtime size and platform implications;
- security posture;
- replaceability behind a QR Commons-owned boundary.

Runtime dependency count should remain deliberately small. Test-only dependencies may be broader when they improve independent conformance, but they must not leak into production bundles.

### 2.6 Operational usability

A technically correct library can still be poor infrastructure if it is difficult to adopt.

QR Commons should optimize for:

- useful error messages;
- obvious defaults;
- documented compatibility;
- copy-pastable examples once APIs exist;
- predictable versioning;
- explicit deprecation policy before stable releases;
- small installation and integration surface;
- clear migration notes for breaking changes;
- documentation useful to both developers and non-specialist implementers.

## 3. Reliability ladder

Features should move through explicit confidence levels rather than simply "implemented / not implemented".

### Experimental

Behavior may change freely. Suitable for exploration, not a compatibility promise.

### Verified

Behavior has deterministic tests and representative conformance coverage.

### Hardened

Behavior has edge-case coverage, compatibility checks, security review appropriate to its risk, and documented operational constraints.

### Stable

Behavior is covered by an explicit compatibility commitment and release/versioning policy.

R0.1 targets **Verified** for the static text-to-matrix-to-SVG path. QR Commons should not use "stable" language merely because a feature works locally.

## 4. Conformance as a first-class asset

The repository's conformance corpus is part of the product.

It should eventually contain:

- representative payload fixtures;
- all supported ECC levels;
- capacity-boundary cases;
- Unicode and normalization cases where relevant;
- expected matrix metadata;
- deterministic SVG expectations;
- independent decode verification;
- malformed input and failure fixtures;
- future styling/logo cases that prove functional patterns remain decodable.

A contributor should be able to change the underlying encoder or renderer and use the conformance corpus to determine whether QR Commons behavior remains acceptable.

## 5. Supply-chain and repository posture

As executable code lands, the project should progressively adopt a security posture suitable for reusable OSS infrastructure.

R0.1/R0.x direction:

- lockfile committed when dependencies exist;
- automated tests on supported Node runtimes;
- minimal GitHub Actions permissions;
- third-party actions pinned to immutable revisions when practical;
- automated dependency updates with human review;
- dependency-diff review for pull requests;
- security reporting policy;
- release artifacts generated by automation rather than developer workstations once releases begin;
- provenance/SBOM evaluation before stable package distribution;
- OpenSSF Scorecard and OSPS Baseline used as external signals/guidance, not as badge collection exercises.

Security controls should correspond to real project risk and maturity. A green badge must never substitute for understanding the dependency and release path.

## 6. Performance and footprint

QR Commons does not need to win synthetic benchmarks, but avoidable cost is contrary to the utility model.

Before stable library releases, establish measurable budgets for:

- core package runtime dependency count;
- installed/package size;
- browser bundle contribution;
- encode/render latency for representative symbols;
- batch throughput;
- memory behavior for large batches.

Budgets should be measured before numerical limits are constitutionalized.

## 7. Compatibility

Compatibility should be stated, tested, and finite.

R0.1 targets:

- Node.js 22 and 24 for library/tooling verification;
- modern evergreen browsers when a browser consumer exists;
- DOM-free core and canonical SVG renderer;
- TypeScript as the source contract without requiring TypeScript at runtime.

Additional runtimes should be added because they are tested and useful, not because the project claims universal JavaScript compatibility.

## 8. Independence from the hosted product

The future hosted QR Commons web surface is a reference client of the same public primitive.

The web product must not become the only place where:

- a valid symbol can be generated;
- an export can be produced;
- correctness can be verified;
- configuration semantics are defined.

A self-hosted or library-only consumer should receive the same correctness guarantees for equivalent capabilities.

## 9. Adoption promise

QR Commons aims to make the following statement increasingly true as it matures:

> You can audit it, run it locally, embed it, self-host it, automate it, export from it, and leave it — without your static QR codes becoming dependent on us.

That promise is the project's primary infrastructure value.