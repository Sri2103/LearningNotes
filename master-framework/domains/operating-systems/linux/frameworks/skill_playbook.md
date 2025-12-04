# Linux Playbook

## General Debug Playbook

1. Identify problem domain: CPU, memory, IO, FS, network
2. Use the right command set
3. Check logs
4. Trace syscalls
5. Inspect kernel-level details

---

## CPU Playbook

- top
- htop
- ps -aux
- pidstat
- perf stat

---

## Memory Playbook

- free -h
- vmstat
- /proc/meminfo
- smem
- check swap usage
- analyze page faults

---

## Disk IO Playbook

- iostat
- df -h
- du -sh
- lsblk
- hdparm

---

## Network Playbook

- ip addr
- ip route
- ss -tulpn
- netstat
- traceroute
- tcpdump

---

## Services Playbook

- systemctl status
- systemctl restart
- journalctl -xe

---

## Filesystem Playbook

- inode usage
- mount
- fstab
- ACLs
