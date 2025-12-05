# JWT Checklist

- short TTL
- signed with HS256/RS256
- store no sensitive data
- use secure cookies

# Password Storage Template

password_hash = bcrypt(password, salt)

# TLS Handshake Steps

client hello → server hello → certificates → key exchange → encrypted traffic

# Threat Model Template

1. asset
2. entry point
3. threat
4. mitigation
