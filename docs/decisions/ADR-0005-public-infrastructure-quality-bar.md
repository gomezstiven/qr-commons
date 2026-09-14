# ADR-0005 — Public infrastructure quality is part of the product contract

Status: **Proposed**  
Date: **2026-09-14**

## Context

QR Commons operates in a category with abundant QR generators. Feature existence alone is not a meaningful differentiator.

The project intends to be usable by individuals, companies, institutions, public bodies, production workflows, and downstream software. Those users need confidence not only in visible features but also in correctness, reproducibility, portability, privacy, dependency discipline, security posture, and long-term operational usability.

If these properties are treated as release polish, the project can easily become a visually capable generator whose reusable core is difficult to audit or depend on.

## Decision

QR Commons treats the following properties as first-class product requirements:

- correctness;
- determinism;
- portability;
- privacy by architecture;
- dependency and supply-chain discipline;
- conformance;
- operational usability;
- explicit compatibility;
- transparent governance and security posture.

The repository's conformance corpus is considered a project asset, not merely an implementation detail.

Runtime dependencies must remain deliberately small, justified, and replaceable behind QR Commons-owned contracts.

The future hosted web surface remains a downstream client of the reusable primitive and must not become required infrastructure for static generation.

The project will use external OSS guidance such as OpenSSF security baselines/Scorecard as inputs and external signals, but will not optimize for badges at the expense of understanding actual project risk.

## Consequences

### Positive

- adoption decisions can rely on explicit non-functional guarantees rather than marketing claims;
- dependency and portability costs are considered before they become difficult to reverse;
- encoder/renderer implementations can change behind conformance-backed contracts;
- enterprise/institutional consumers gain clearer evidence for evaluation;
- the hosted product cannot silently become a mandatory service dependency.

### Costs

- features may ship more slowly because conformance and documentation are required;
- some abstractions will be deferred until real behavior justifies them;
- repository/security/release discipline requires ongoing maintenance;
- the project must be willing to reject attractive features that materially weaken reliability or portability.

## Related

- `docs/architecture/PUBLIC-INFRASTRUCTURE.md`
- `docs/milestones/R0.1.md`
- `SECURITY.md`
- `GOVERNANCE.md`
