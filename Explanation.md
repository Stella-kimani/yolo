
---

### Explanation.md

```markdown
# Kubernetes Implementation Explanation

## 1. Kubernetes Objects Selection

### StatefulSet for MongoDB
- Guarantees stable network identifiers
- Maintains persistent storage
- Ensures ordered deployment/scaling
- Uses volumeClaimTemplate for storage

### Deployment for Services
- Frontend and backend as Deployments
- Rolling update capability
- Horizontal scaling support
- Liveness/readiness probes

## 2. Network Exposure Strategy

### Service Types
| Service       | Type      | Purpose                     |
|---------------|-----------|-----------------------------|
| frontend-svc  | NodePort  | External access             |
| backend-svc   | ClusterIP | Internal communication      |
| mongodb-svc   | ClusterIP | Headless service for StatefulSet |

## 3. Persistent Storage Solution

### MongoDB Data Persistence
- PVC with 1GB storage request
- Standard storage class
- Retains data through pod restarts
- Example configuration:
```yaml
volumeClaimTemplates:
- metadata:
    name: mongo-storage
  spec:
    accessModes: [ "ReadWriteOnce" ]
    resources:
      requests:
        storage: 1Gi
