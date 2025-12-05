# Web Dev Playbook

## Frontend Playbook

1. Break UI into components
2. Start with static version
3. Add interactivity
4. Derive state from data, not UI
5. Lift state up when needed
6. Use React Query/SWR for async
7. Optimize re-renders

---

## CSS Playbook

- mobile-first
- use flexbox/grid
- use utility classes
- avoid deep nesting
- use responsive units

---

## Backend Playbook

1. define endpoints
2. build route handlers
3. validate input
4. connect database
5. write queries
6. handle errors globally
7. separate concerns (services/controllers)

---

## Auth Playbook

Session-based:

- server stores session
- secure cookies
- CSRF protection

JWT-based:

- short expiry
- refresh tokens
- never store JWT in localStorage

OAuth2/OIDC:

- use providers for sign-in
- store tokens securely

---

## Performance Playbook

- caching headers
- CDN
- image optimization
- lazy loading
- DB indexes
- pagination

---

## Security Playbook (OWASP)

- sanitize inputs
- parameterized queries
- secure cookies
- fix CORS
- limit requests
- disable directory listing
