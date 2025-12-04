# resource enforcements

## task: create and enforce cpu/memroy quota in namespace

### create a namespace

```bash
    kubectl create ns limits-lab
```

### Apply resource quota

```yaml
cat <<EOF | kubectl apply -n limits-lab -f -
apiVersion: v1
kind: ResourceQuota
metadata:
    name: compute-quota
spec:
    hard:
        pods: "2"
        limits.cpu: "2"
        limits.memory: "1Gi"
EOF
```

### Apply Limit Range

```yaml
cat <<EOF | kubectl apply -n limits-lab -f -
apiVersion: v1
kind: LimitsRange
metadata:
    name: default-limits
spec:
    limits:
    - default:
        cpu: 500m
        memory: 256Mi
      defaultRequest:
        cpu: 200m
        memory: 128Mi
      type: Container
EOF
```
