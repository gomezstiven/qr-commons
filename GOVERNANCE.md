# Governance

QR Commons is currently an independent maintainer-led open-source project.

This document describes the project's present governance state. It is intentionally lightweight and should evolve when contributor activity and project adoption justify additional structure.

## 1. Maintainer

The current lead maintainer is Stiven Gómez Barrientos (`@gomezstiven`).

The maintainer is responsible for:

- repository administration;
- release decisions;
- architectural coherence;
- security response coordination;
- contributor review and moderation;
- deciding when an experimental contract is ready to become stable.

## 2. Decision model

Routine implementation decisions are made through pull-request review.

Durable decisions that materially affect public contracts, architecture, licensing, compatibility, security posture, or project boundaries should be documented in an Architecture Decision Record (ADR).

Important design work should remain visible in public issues and pull requests whenever security or embargo constraints do not require otherwise.

## 3. Contributions

Contributions are accepted under the repository's Apache-2.0 license terms unless explicitly stated otherwise.

QR Commons does not currently require a Contributor License Agreement (CLA).

Submitting a contribution does not guarantee acceptance. Changes may be declined because of architecture, maintenance cost, dependency footprint, compatibility, security, usability, scope, or insufficient evidence that a new abstraction is needed.

## 4. Public API stewardship

A public API is a maintenance commitment, not merely an exported function.

Before stable releases, APIs may change. The project should avoid promoting APIs to stable status until there is:

- real usage evidence;
- conformance coverage;
- clear ownership of errors and configuration semantics;
- a compatibility policy;
- a credible maintenance path.

## 5. Maintainer expansion

Additional maintainers may be added after sustained high-quality contribution and demonstrated alignment with project principles.

Maintainer access should follow least-privilege principles and should not be granted solely because of organizational affiliation or project sponsorship.

If the maintainer group grows, this document should be revised to define:

- maintainer nomination/removal;
- voting or consensus rules where needed;
- release authority;
- security-team responsibilities;
- conflict-resolution procedures.

## 6. Sponsorship and commercial use

QR Commons may be used commercially under Apache-2.0.

Financial support, sponsorship, consulting relationships, or commercial products built around QR Commons do not automatically grant governance rights or the ability to redefine the open-source project boundary.

The static generation utility should not be intentionally degraded to manufacture a proprietary dependency.

## 7. Independence

QR Commons is maintained under the author's personal open-source identity and is not governed by Evenn or by a QR-resolution commercial service.

Organizations may use, sponsor, contribute to, or build on the project without becoming required infrastructure for it.

## 8. Evolution

Governance should grow in proportion to real community and adoption needs.

The project should prefer transparent, comprehensible governance over premature committees or process overhead.