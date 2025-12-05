# Virtualization & Containers Skill Map

## Virtualization Fundamentals

- hypervisors
- VM lifecycle
- CPU virtualization
- VT-x/AMD-V
- memory virtualization

---

## Containers Fundamentals

- Docker basics
- images
- layers
- build context
- OCI basics

---

## Linux Kernel Isolation

### Namespaces

- PID
- NET
- Mount
- UTS
- IPC
- User
- Cgroup namespace

### Cgroups

- CPU
- memory
- devices
- limits
- blkio
- pids

---

## Container Internals

- containerd
- runc
- overlayfs
- union filesystems
- chroot vs pivot_root
- seccomp
- capabilities
- AppArmor/SELinux

---

## Networking

- cNI basics
- veth pairs
- bridges
- NAT
- DNS inside containers

---

## Storage

- container layers
- overlay2
- image caching
- volumes/bind mounts

---

## Advanced

- building container runtime
- sandboxing
- rootless containers
- CRI layer in Kubernetes
