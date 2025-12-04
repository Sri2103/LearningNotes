# Golang Skill Playbook

## When starting a Go program

1. Identify input & output
2. Define structs & types first
3. Add methods to organize behavior
4. Add error handling early
5. Keep functions small

---

## Concurrency Playbook

When to use goroutines:

- Network calls
- I/O
- CPU-light parallel tasks

When NOT to use:

- Complex inter-goroutine communication
- Shared state without protection

Concurrency patterns:

- Worker pool
- Fan-in / fan-out
- Pipeline
- Context cancellation

---

## Interfaces Playbook

Use interfaces:

- For behavior, not data
- At the consumer side (not producer)
- Keep interfaces ~1–2 methods

---

## Error Handling Playbook

- Always return `error`
- Wrap errors with context
- Avoid panics except initialization

---

## HTTP Server Playbook

1. Create handlers
2. Pass dependencies as interfaces
3. Use context for timeouts
4. Log everything
5. Add graceful shutdown

---

## Testing Playbook

- Use table-driven tests
- Use benchmarks for performance
- Avoid global state
