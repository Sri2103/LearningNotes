# DevOps/SRE Playbook

## Incident Debug Playbook
1. Check service status  
2. Check logs  
3. Check metrics (CPU/mem/error rate)  
4. Check recent deployments  
5. Check network reachability  
6. Check dependencies  
7. Engage team if needed  
8. Document RCA  

---

## CI/CD Playbook
- Use pipelines for tests  
- Use environments (dev/stage/prod)  
- Use approvals  
- Always version artifacts  
- Use rollback points  

---

## IaC Playbook
Terraform:
- Plan → Apply  
- Use modules  
- Version state  
- Never modify cloud resources manually  

Ansible:
- Idempotency  
- Roles  
- Handlers  
- Inventory management  

---

## Kubernetes Playbook
1. Check pods/nodes  
2. Check events  
3. Check logs  
4. Check networking (svc, ingress)  
5. Check resource limits  
6. Check autoscaling  

---

## Observability Playbook
Metrics → Prometheus  
Logs → Loki/ELK  
Tracing → Jaeger  
Dashboards → Grafana  
Alerts → actionable, low-noise  

---

## Reliability Playbook
- SLO definition  
- Error budgets  
- Load testing  
- HA patterns  
- Failover and backups  
