# Intermediate Container Internals

## Union Filesystems

- overlayfs
- diff layers
- lowerdir, upperdir, workdir

## OCI Runtime (runc)

- OCI spec
- config.json
- runc create → start → kill

## containerd Architecture

- shim process
- snapshotters
- image store

## Rootless Containers

- user namespace mapping
- restrictions

## Networking Internals

- veth pairs
- bridges
- NAT
- iptables
