# Kubernetes Playbook

## YAML Playbook

1. apiVersion
2. kind
3. metadata
4. spec

## Pod Debugging Playbook

1. `kubectl get pods`
2. `kubectl describe pod <name>`
3. Check events for scheduling errors
4. `kubectl logs <pod>`
5. Check liveness/readiness probe status

## Node Debugging Playbook

- `kubectl get nodes`
- `kubectl describe node`
- Check conditions: MemoryPressure, DiskPressure, PIDPressure

## Deployment Strategy Playbook

- Use RollingUpdate by default
- Set maxUnavailable / maxSurge
- Use readiness gates

## Service Playbook

ClusterIP → internal communication  
NodePort → outside node access  
LoadBalancer → cloud-level external access

## Config Playbook

ConfigMap → non-sensitive configs  
Secret → sensitive configs  
Mount vs ENV vs Volume

## Networking Playbook

- Pods communicate directly
- Services create stable virtual IP
- Ingress exposes HTTP externally

## Controller Playbook

- Reconcile desired vs actual state
- Informers watch resources
- Update, create, delete logic
