# Minimal Dockerfile Template

FROM alpine
COPY app /app
CMD ["/app"]

# CPU Cgroup Limit

echo 50000 > cpu.cfs_quota_us

# Network Namespace Setup

ip netns add ns1
ip link add veth0 type veth peer name veth1
