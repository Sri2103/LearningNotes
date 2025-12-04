# Golang Mistake Log

## Common Mistakes I've Made

- Using channels where a mutex is better
- Returning nil pointer receivers
- Forgetting to close goroutines
- Using slice incorrectly (capacity vs length)
- Incorrectly copying slices
- Misusing defer inside loops
- Forgetting to check errors

## Fix Strategy

- Revisit concurrency playbook
- Write small reproducible tests
- Re-read Go memory model
- Benchmark small examples

## Recent mistakes

-
-
