# OS Trigger Checklist

- Slow app → check context switches
- High latency → check page faults
- High CPU → check scheduler
- High IO wait → disk or filesystem issue
- Strange hangs → deadlock or contention
- Memory leak → check heap allocation + page tables
