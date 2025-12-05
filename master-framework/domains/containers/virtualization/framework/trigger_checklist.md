# Containers Trigger Checklist

- too much CPU → adjust cgroups CPU quota
- OOMKilled → increase mem.limit or fix app
- slow builds → check layer caching
- DNS issues → check container resolv.conf
- container cannot ping → check network namespace
- images too large → multi-stage build
