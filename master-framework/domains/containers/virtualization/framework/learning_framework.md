# Virtualization & Containers Learning Framework

## 1. Why am I learning this?

> To understand how containers work at the OS/kernel level, how Docker builds and runs containers, and how virtualization enables cloud-native and modern platform stacks.

## 2. Subskills (Decomposition)

### Virtualization

- full virtualization (KVM/QEMU)
- para-virtualization
- hardware virtualization
- hypervisors (Type 1 & Type 2)
- VM memory & CPU isolation

### Containers (Linux kernel-based)

- namespace isolation
- cgroups resource control
- overlay/union filesystems
- container images & layers
- OCI runtime (spec + runc)
- container daemons
- rootless containers
- container networking
- container storage

### Ecosystem

- Docker
- containerd
- CRI-O
- Podman
- runc
- BuildKit

### Low-Level Linux Internals

- syscalls
- chroot
- pivot_root
- mount namespace
- seccomp
- capabilities

## 3. Knowledge Map

Fundamentals → Docker + basic namespaces  
Intermediate → OCI, cgroups, image layers  
Advanced → writing your own container runtime + virtualization

## 4. Core Resources

Books:

- Docker Deep Dive
- Linux Kernel Development
- Container Security

Courses:

- Kelsey Hightower: “Containers the Hard Way”
- Linux Foundation LXC/LXD courses

## 5. Learning Method

Understand → break into pieces → rebuild → implement your own mini-container runtime

## 6. Practice Plan

Daily: learn one namespace or cgroup  
Weekly: build a container feature  
Monthly: implement your own container runtime

## 7. Containers Playbook

1. Identify isolation needs
2. Choose namespaces
3. Apply cgroups
4. Build root filesystem
5. Start process with runc-like flow
6. Add network + mounts
7. Apply security (seccomp/caps)

## 8. Common Mistakes

- misunderstanding namespace boundaries
- wrong cgroup configuration
- mixing user and PID namespaces
- incorrect rootfs mounts
- assuming containers = VMs
