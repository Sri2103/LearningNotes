# config-map

the variables to be added to configuration of applications deployed into cluster

## creating a raw config map

create a config map by adhoc

```bash
kubectl create configmap app-config --from-literal=ENV=production --from-literal=VERSION=2.0
```

adding it a pod using this config map , this is an example for heredoc piping

```yaml
cat <<EOF | kubectl apply -f -
apiVersion: v1
kind: Pod
metadata:
    name: config-pod
spec:
    containers:
    - name: test
      image: busybox
      command: ["sh", "-c", "sleep 3600"]
      envFrom:
      - configMapRef:
          name: app-config
EOF
```

## validating config created

### check config

```bash
   kubectl describe configmap app-config
```

### ensure the pod is running

```bash
kubectl exec -it config-pod --sh
```

### Modifying the configurations

```bash
kubectl edit configmap app-config
kubectl delete pod config-pod
```
