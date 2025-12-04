# configuring volume to container

we are using emptyDir

## configuring Pod

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: redis
spec:
  containers:
    - name: redis
      image: redis
      volumeMounts:
        - name: redis-storage
          mountPath: /data/redis
  volumes:
    - name: redis-storage
      emptyDir: {}
```

## exploring the pods

```bash
kubectl exec -it redis -- /bin/bash
```

## cleanup pods

```bash
kubectl delete pod redis
```
