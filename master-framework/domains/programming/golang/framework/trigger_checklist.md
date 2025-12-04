# Golang Trigger Checklist

- Need speed → use slices, not linked lists
- Need concurrency → goroutines + channels
- Need I/O → use bufio
- Need safe sharing → sync.Mutex or sync.Map
- Need cancellation → context.WithCancel
- Need periodic tasks → time.Ticker
- Need HTTP server → net/http
- Need CLI → cobra or flag
- Need file reading → os and bufio
