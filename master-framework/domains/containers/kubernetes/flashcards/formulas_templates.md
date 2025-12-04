# Deployment Template

apiVersion: apps/v1
kind: Deployment
...

# Service Template

apiVersion: v1
kind: Service
...

# Probe Template

livenessProbe:
httpGet:
path: /health
port: 8080
