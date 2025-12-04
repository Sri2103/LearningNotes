# Kubernetes Trigger Checklist

- Need long-running app → Deployment
- Need one-per-node → DaemonSet
- Need ordered identity → StatefulSet
- Need internal communication → ClusterIP
- Need external access → Ingress / LoadBalancer
- Need environment config → ConfigMap
- Need secrets → Secret
- Need storage → PVC + StorageClass
- Need autoscaling → HPA
- Need to enforce rules → NetworkPolicy
- Need custom logic → Controller / Operator
