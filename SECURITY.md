# Security Policy

QR Commons is currently pre-alpha.

Please do not disclose security-sensitive findings in a public issue when they could expose users or downstream consumers. Use GitHub's private vulnerability reporting if enabled for the repository; otherwise contact the maintainer through the contact method published on the maintainer's GitHub profile.

Particular areas of interest include:
- unsafe handling of structured payloads;
- injection into SVG or exported artifacts;
- unexpected network transmission of user payloads;
- dependency-chain vulnerabilities;
- malformed exports that create misleading or different destinations.
