# Security & Crypto Trigger Checklist

- Sending data → apply encryption
- Storing secrets → use KMS or Vault
- Exposing API → rate-limit & authenticate
- Handling passwords → use bcrypt/argon2
- Writing cookies → secure + HttpOnly + SameSite
- Deploying service → check TLS cert
- Designing system → map threat boundaries
