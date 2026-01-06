# MERN Stack Kubernetes Deployment Guide

## Files Created
- `namespace.yaml` - Namespace configuration
- `frontend.yaml` - Frontend deployment and NodePort service
- `backend.yaml` - Backend deployment and NodePort service
- `mongodb.yaml` - MongoDB deployment with PVC and ClusterIP service

## Deployment Steps

### 1. Create the namespace
```bash
kubectl apply -f namespace.yaml
```

### 2. Deploy MongoDB
```bash
kubectl apply -f mongodb.yaml
```

### 3. Deploy Backend
```bash
kubectl apply -f backend.yaml
```

### 4. Deploy Frontend
```bash
kubectl apply -f frontend.yaml
```

## Verify Deployment

### Check all resources in the namespace
```bash
kubectl get all -n 22i2460-mern-app
```

### Check PVC status
```bash
kubectl get pvc -n 22i2460-mern-app
```

## Access the Application

- **Frontend**: `http://<node-ip>:30173`
- **Backend**: `http://<node-ip>:30300`
- **MongoDB**: Accessible internally via `mongodb-service:27017`

## Resource Summary

| Component | Replicas | Port | Service Type | Node Port |
|-----------|----------|------|--------------|-----------|
| Frontend  | 2        | 8888 | NodePort     | 30173     |
| Backend   | 2        | 6868 | NodePort     | 30300     |
| MongoDB   | 1        | 27017| ClusterIP    | N/A       |

## Clean Up

To remove all resources:
```bash
kubectl delete namespace 22i2460-mern-app
```
