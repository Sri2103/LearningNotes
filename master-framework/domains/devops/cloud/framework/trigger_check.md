# Cloud Computing Trigger Checklist

- Traffic spike → autoscaling + LB
- High latency → check networking + DNS
- High cost → unused VMs or wrong tier storage
- Security alerts → IAM review
- DB slow → wrong instance size or no read replicas
- Regional outage → failover plan needed
