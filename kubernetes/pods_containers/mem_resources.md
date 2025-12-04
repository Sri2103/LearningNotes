# Assign memory resources to pod and containers -- from official tasks

- how to assign memory request and memory limits to the container and pods
- container can have as much memory it can, but cannot use more than it is permitted

## step1: check if metrics server is available

```bash
kubectl get apiservices | grep metric
```

## scenario-1 basic implementation

- create the corresponding **namespace** for the resource

```bash
kubectl create ns mem-example
```

- specify the standard memroy quota and memory request

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: memory-demo
  namespace: mem-example
spec:
  containers:
    - name: memory-demo-ctr
      image: polinux/stress
      resources:
        requests:
          memory: "100Mi"
        limits:
          memory: "200Mi"
      command: ["stress"]
      args: ["--vm", "1", "--vm-bytes", "150M", "--vm-hang", "1"]
```

- create the pod with above config and ensure it is running

- verify the pod description and its running

```bash
    kubectl get pod memory-demo --output=yaml --namespace=mem-example
```

check for resources for memory request and limit

- check the resources used by this pod

```bash
kubectl top pod memory-demo --namespace=memexample
```

## scenario-2 if pod exceeds the memroy limit

- generate the pod manifest with excess memory requirement than given to ns

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: memory-demo-2
  namespace: mem-example
spec:
  containers:
    - name: memory-demo-2-ctr
      image: polinux/stress
      resources:
        requests:
          memory: "50Mi"
        limits:
          memory: "100Mi"
      command: ["stress"]
      args: ["--vm", "1", "--vm-bytes", "250M", "--vm-hang", "1"]
```

- try to create the pod with above config and see if the pod runs or not
- try describing the pod with status
- my find the following status

```bash
NAME            READY     STATUS      RESTARTS   AGE
memory-demo-2   0/1       OOMKilled   1          24s
```

## scenario-3: if memory request is too big for the node

- specify a 1GB memory request pod

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: memory-demo-3
  namespace: mem-example
spec:
  containers:
    - name: memory-demo-3-ctr
      image: polinux/stress
      resources:
        requests:
          memory: "1000Gi"
        limits:
          memory: "1000Gi"
      command: ["stress"]
      args: ["--vm", "1", "--vm-bytes", "150M", "--vm-hang", "1"]
```

- when tried to apply, the pod will be in pending state, as the kubelet could not find the node to deploy it to
