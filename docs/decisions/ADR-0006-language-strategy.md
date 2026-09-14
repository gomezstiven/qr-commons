# ADR-0006 — English canonical technical language, Spanish first official translation

Status: **Proposed**  
Date: **2026-09-14**

## Context

QR Commons is intended for broad international use while also having a strong usability opportunity in Latin America.

Using multiple languages without an explicit authority model can create conflicting specifications, stale translations, inconsistent API terminology, and contributor friction. Using English only would simplify maintenance but unnecessarily reduce accessibility for Spanish-speaking users, institutions, operators, and contributors.

## Decision

English is the canonical technical language for:

- source code and identifiers;
- package names and public APIs;
- commit messages and pull-request titles;
- ADRs;
- normative technical specifications and compatibility contracts;
- machine-consumed repository configuration.

Spanish is the first officially maintained translation language.

The project will maintain high-value Spanish entry points beginning with the README and contributor onboarding and will design the future hosted web surface with English and Spanish as first-class locales.

Issues and discussions may be opened in either English or Spanish. Actionable Spanish reports do not require contributor-provided translation before triage.

When a translated document mirrors a normative English document, the English source remains authoritative in the event of conflict.

## Consequences

### Positive

- code and API vocabulary remain globally consistent;
- Spanish-speaking users and contributors receive a first-class adoption path;
- Latin American organizations can evaluate and introduce the project with less language friction;
- translation effort can focus on high-value surfaces rather than duplicating every internal file.

### Costs

- maintained translations create synchronization work;
- repository changes must consider whether an official translation needs follow-up;
- wording must be managed carefully to avoid domain-term drift between languages.

## Implementation

Current entry points:

- `README.md` / `README.es.md`
- `CONTRIBUTING.md` / `CONTRIBUTING.es.md`
- `docs/LANGUAGE-POLICY.md`

Future user-facing web content should use locale-aware presentation rather than embedding language-specific strings into reusable QR logic.
