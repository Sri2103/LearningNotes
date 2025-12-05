# Security & Cryptography Playbook

## Threat Modeling Playbook

STRIDE:

- Spoofing
- Tampering
- Repudiation
- Information disclosure
- Denial of service
- Elevation of privilege

Steps:

1. Identify system components
2. Identify entry points
3. Analyze trust boundaries
4. Think like attacker
5. Propose mitigations
6. Validate periodically

---

## Authentication & Authorization Playbook

- Prefer OIDC & OAuth2
- Avoid storing passwords → use salted bcrypt/argon2
- Use JWT carefully → short TTL, signature, no sensitive data
- Use session binding + CSRF protections

---

## Crypto Playbook

Hashing:

- bcrypt/argon2 → passwords
- SHA-256/SHA-3 → general hashing

Symmetric:

- AES-256-GCM → encryption

Asymmetric:

- RSA/ECC → key exchange, signatures

Key Exchange:

- Diffie-Hellman
- Elliptic curve Diffie-Hellman

PKI:

- certificate chains
- CA → intermediate → leaf

TLS:

- TLS handshake
- session resumption
- PFS

---

## Secure Coding Playbook

- validate input
- sanitize outputs
- parameterized queries (SQLi prevention)
- escape HTML (XSS prevention)
- rate limiting
- logging + monitoring
- principle of least privilege

---

## Cloud Security Playbook

- IAM roles
- security groups
- key rotation
- secret managers
- encryption-at-rest
- encryption-in-transit
