# Containers & Virtualization Mistake Log

## Common Mistakes I've Made

- using latest tag
- layering too much in images
- breaking mount namespaces
- wrong network bridge setup
- misconfiguring user namespaces
- unbounded container resources (memory leak crashes host)
- forgetting --cap-drop ALL

## Fix Strategy

- pin image versions
- list namespaces
- inspect cgroups
- monitor container metrics
- add resource limits default
