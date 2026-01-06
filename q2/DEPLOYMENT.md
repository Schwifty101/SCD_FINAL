## Q2 

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

## Clean Up

To remove all resources:

```bash
kubectl delete namespace 22i2460-mern-app
```
