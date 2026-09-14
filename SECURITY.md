# Security Policy

QR Commons is currently pre-alpha. Security posture and reporting processes will harden as executable code and releases are introduced.

## Reporting a vulnerability

Please do **not** disclose security-sensitive findings in a public issue when disclosure could expose users, downstream consumers, package users, or a reproducible exploit path.

Preferred reporting path:

1. Use GitHub Private Vulnerability Reporting when it is enabled for this repository.
2. If private reporting is unavailable, contact the maintainer through the contact method published on the maintainer's GitHub profile and clearly identify the message as a security report.

A useful report includes:

- affected commit/version;
- affected package or surface;
- reproduction steps or proof of concept;
- expected vs observed behavior;
- practical impact;
- whether the issue is already public elsewhere;
- suggested mitigation, if known.

Do not include real sensitive QR payloads when a synthetic reproduction is sufficient.

## Security-relevant areas

Particular areas of interest include:

- payload transformation that changes the destination/content unexpectedly;
- injection into SVG or other exported artifacts;
- unsafe treatment of structured payloads;
- unexpected network transmission of QR contents;
- dependency or build-chain compromise;
- malicious or ambiguous Unicode handling;
- unsafe file/export naming or content handling;
- rendering behavior that can create a visually plausible but semantically different artifact;
- future logo/styling transformations that break protected QR structures;
- release/package provenance problems once distribution begins.

## Security properties of the project

QR Commons is designed around several architectural security/privacy properties:

- static generation should not require QR Commons-controlled redirects;
- reusable core libraries should not require network access;
- the hosted web application should not need to transmit payload contents for normal static generation;
- runtime dependencies should remain deliberately small and replaceable;
- test conformance should use independent implementations where useful to avoid self-confirming failures;
- release automation, provenance, and supply-chain controls should mature before stable distribution.

These are project goals and architecture constraints, not a claim that pre-alpha code is vulnerability-free.

## Supported versions

No stable version is currently supported. Until the project begins versioned releases, security fixes apply to the current development line.

A version support table will be added before stable releases.

## Coordinated disclosure

The maintainer will aim to:

- acknowledge actionable private reports;
- reproduce and assess impact;
- prepare a fix before unnecessary public disclosure when users could be harmed;
- credit reporters who want attribution;
- publish security advisories when a released version is materially affected.

QR Commons does not currently promise a formal response-time SLA.

## Non-security reports

Incorrect output that does not create a security-sensitive condition can be filed through the normal bug-report template. When in doubt, prefer private reporting first.