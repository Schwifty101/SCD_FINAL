# Q1


### 1. Build and Start All Services
```bash
docker-compose up -d --build
```
- Builds all Docker images from Dockerfiles in detached mode

### 2. Check Running Containers
```bash
docker-compose ps
```
Shows status of all services 

### 3. View Service Logs
```bash
# All services
docker-compose logs -f

# Specific service
docker-compose logs -f api-gateway
docker-compose logs -f auth-service
```

### 4. Stop All Services
```bash
docker-compose down
```
Stops and removes containers, networks

### 5. Stop and Clean Everything
```bash
docker-compose down -v
```
Removes containers, networks, and volumes

---

## Testing the API

### Register a New User
```bash
curl -X POST http://localhost:4000/auth/register \
  -H "Content-Type: application/json" \
  -d '{"email":"test@example.com","password":"test123","role":"patient"}'
```

### Login
```bash
curl -X POST http://localhost:4000/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email":"test@example.com"}'
```

### Get Doctors List
```bash
curl http://localhost:4000/doctors
```

### Book Appointment
```bash
curl -X POST http://localhost:4000/appointments \
  -H "Content-Type: application/json" \
  -d '{"userId":"1","doctorId":"2","date":"2026-01-15"}'
```

### Get Appointments
```bash
curl http://localhost:4000/appointments
```

### Health Check
```bash
curl http://localhost:4000/health
```

---

## Docker Hub Commands

### Login to Docker Hub
```bash
docker login
```

### Build Images
```bash
docker-compose up -d --build
```

### Push Images to Docker Hub
```bash
docker-compose push
```

### Pull Images from Docker Hub
```bash
docker-compose pull
```

---

## Docker Hub Links

- API Gateway: https://hub.docker.com/r/schwifty404/api-gateway
- Auth Service: https://hub.docker.com/r/schwifty404/auth-service
- Patient Service: https://hub.docker.com/r/schwifty404/patient-service
- Doctor Service: https://hub.docker.com/r/schwifty404/doctor-service
- Appointment Service: https://hub.docker.com/r/schwifty404/appointment-service
- Notification Service: https://hub.docker.com/r/schwifty404/notification-service

---

## GitHub Actions CI/CD

The `.github/workflows/build-and-push.yml` workflow automatically

---