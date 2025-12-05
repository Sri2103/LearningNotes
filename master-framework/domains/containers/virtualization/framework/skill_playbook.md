# Containers Playbook

## Namespace Playbook

Use:

- PID → isolate process tree
- NET → isolate network stack
- UTS → hostname isolation
- Mount → isolated filesystem
- User → UID/GID mapping
- IPC → shared memory isolation
- Cgroup → resource limits

---

## Cgroups Playbook

Set:

- CPU quota/period
- memory.limit_in_bytes
- pids.max
- blkio throttling

Workflow:

1. create cgroup folder
2. write limits
3. add process to cgroup

---

## Container Build Playbook

1. choose base image
2. understand union layers
3. minimize layers
4. reduce build context
5. use multi-stage builds

---

## Networking Playbook

1. create veth pair
2. move one end to container netns
3. attach host end to bridge
4. add NAT & IP routing

---

## Security Playbook

- disable privileged mode
- drop capabilities
- use seccomp deny list
- use AppArmor/SELinux profiles
- read-only rootfs

---

## Image Optimization Playbook

- use alpine or distroless
- multi-stage builds
- remove build tools
- cache layers effectively

---

## Debug Playbook

- inspect filesystem
- inspect namespaces
- inspect cgroups
- inspect image layers
