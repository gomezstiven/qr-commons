# Language Policy

Status: **PROPOSED for R0.1**

QR Commons is an international open-source project with an intentional first-class path for Spanish-speaking users and contributors, especially across Latin America.

## 1. Canonical technical language

English is the canonical language for:

- source code and identifiers;
- package names and public APIs;
- commit messages;
- pull request titles;
- issue templates and machine-consumed repository configuration;
- Architecture Decision Records (ADRs);
- normative technical specifications and compatibility contracts.

This reduces ambiguity in the codebase and keeps the project accessible to the widest engineering ecosystem.

## 2. Official Spanish documentation

Spanish is the first officially maintained translation language.

The project should provide Spanish versions of high-value entry points, beginning with:

- `README.es.md`;
- contributor onboarding when useful;
- user-facing web documentation;
- guides intended for operators, institutions, and non-specialist implementers.

Spanish documentation is not treated as a community-only afterthought. It is part of the project's usability strategy.

## 3. Canonical vs translated documents

When a translated document mirrors a normative English document:

- the English version remains canonical if interpretations conflict;
- translations must link back to the canonical source;
- the translation should state its synchronization status when exact parity matters;
- material changes to the canonical document should include a translation follow-up when a maintained translation exists.

This rule avoids having two competing technical specifications.

## 4. Translation structure

For short top-level entry points, use language suffixes:

- `README.md`
- `README.es.md`
- `CONTRIBUTING.md`
- `CONTRIBUTING.es.md`

For a larger future documentation site, language-specific navigation may move to locale directories such as `docs/es/` and `docs/en/` without changing the canonical-language rule.

## 5. Issues and discussions

Contributors may open issues and participate in discussions in English or Spanish.

Maintainers should not require a contributor to translate an otherwise actionable Spanish report before it can be triaged. A short English technical summary may be added by maintainers when useful for broader participation.

Code-facing artifacts produced from the discussion remain in English.

## 6. Web product

The future hosted web surface should treat `en` and `es` as first-class locales from the beginning of user-facing implementation.

Do not hard-code English strings throughout reusable logic. User-facing localization belongs to the application/presentation layer and must not leak into core QR contracts.

## 7. Translation quality

Prefer accurate domain language over literal translation.

Terminology should remain consistent across:

- QR generation;
- static vs dynamic behavior;
- payloads;
- error correction;
- quiet zones;
- export formats;
- validation and conformance;
- privacy and local-first behavior.

A terminology/glossary file may be introduced when the translated surface becomes large enough to justify it.

## 8. Additional languages

Additional official translations are welcome when there is enough contributor capacity to maintain them.

The project should prefer a small number of maintained translations over a large set of stale ones.