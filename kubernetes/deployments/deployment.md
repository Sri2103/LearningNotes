# Deployment manual

## let's create a deployment

create a basic nginx deployment for 3 replicas

```bash
 kubectl create deployment nginx-app --image=nginx:latest --replicas=3
```

exposing the deployment via node port

```bash
    kubectl expose deployment nginx-app --port=80 --type=NodePort
```

fetching the service associated with the deployment

```bash
kubectl get svc nginx-app
```

delete the cluster

```bash
kubectl delete deployment nginx-app
```
