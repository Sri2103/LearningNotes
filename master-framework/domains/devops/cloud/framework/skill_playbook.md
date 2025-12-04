# Cloud Computing Playbook

## VPC Playbook

- Create VPC
- Create subnets (public/private)
- Route tables
- NAT gateway
- Internet gateway
- Security groups / firewall rules

## Compute Playbook

VMs:

- choose size
- assign network/security
- attach storage

Containers:

- cluster or serverless
- autoscaling
- service mesh

Serverless:

- event-driven
- ephemeral compute
- cost optimizations

## Storage Playbook

Object → static assets, logs  
Block → databases, VMs  
File → shared volumes

## Database Playbook

SQL:

- read replicas
- high availability
- backups

NoSQL:

- partition keys
- consistency models
- throughput

## Load Balancing Playbook

- L4 LB → TCP/UDP
- L7 LB → HTTP routing, SSL termination

## HA/DR Playbook

- multi-zone
- multi-region
- active-active
- backup & restore

## Cost Optimization Playbook

- right-sizing
- autoscaling
- serverless for bursty workloads
- archival storage
- reserved instances (if provider supports)
