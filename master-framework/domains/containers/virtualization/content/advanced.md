# Advanced Virtualization & Container Concepts

## Kernel Features

- seccomp
- capabilities
- AppArmor/SELinux
- mount propagation
- pivot_root vs chroot

## Low-Level Container Creation

1. clone(CLONE_NEWPID, ...)
2. mount rootfs
3. set hostname
4. configure network
5. apply cgroups
6. exec init

## Virtualization Advanced

- KVM internals
- QEMU
- virtio drivers
- memory ballooning
- CPU pinning
- nested virtualization

## Container Storage

- overlay2 deep dive
- copy-on-write performance
- snapshotting

## Containers in Kubernetes

- CRI
- containerd-shim
- pause container
