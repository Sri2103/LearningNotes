# Security & Cryptography Mistake Log

## Common Mistakes I've Made

- Storing plaintext secrets
- Using weak hashing algorithms
- Incorrectly handling JWT expiration
- Misconfigured CORS
- Forgetting HTTPS enforcement
- Running with admin privileges
- Not validating certificate chains

## Fix Strategy

- Default to encryption
- Use KMS/Vault
- Rotate keys
- Enforce HTTPS
- Use secure cookie flags
