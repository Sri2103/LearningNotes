# Linux Trigger Checklist

- High CPU → check processes + perf
- Slow system → check IO wait
- Low memory → check caches + swap
- Network not working → check ip addr + routing
- Service down → journalctl
- Disk full → df, du
- Strange errors → dmesg
