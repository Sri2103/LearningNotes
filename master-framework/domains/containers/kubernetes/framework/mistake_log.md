# Kubernetes Mistake Log

## Common Mistakes I've Made

- Wrong selectors in Deployments/Services
- Using latest tag in images
- Not checking events before debugging
- Using NodePort unnecessarily
- Hardcoding resource requests/limits
- Applying YAML without version control

## Fix Strategy

- Always validate selectors
- Always read events before panicking
- Use `kubectl explain`
- Use kustomize/helm for environments

## Recent Mistakes

-
-
