# 🚀 Complete DevOps Project – CI/CD, Kubernetes & Monitoring

An end-to-end **production-style DevOps project** demonstrating how to build, containerize, deploy, and monitor a web application using modern DevOps tools and best practices.

---

## 📌 Project Overview

This project covers the full DevOps lifecycle:

- Application development using Python (Flask)
- Containerization with Docker
- CI/CD automation using GitHub Actions
- Deployment to Kubernetes
- Service exposure via NodePort
- Monitoring with Prometheus and Grafana

---

## 🧠 System Architecture

```text
User
 ↓
GitHub Repository
 ↓
GitHub Actions (CI/CD)
 ↓
Docker Image (DockerHub)
 ↓
Kubernetes Cluster
 ↓
Application Service
 ↓
Prometheus & Grafana Monitoring
```

---

## 🛠️ Tech Stack

- **Programming Language:** Python  
- **Framework:** Flask  
- **Containerization:** Docker  
- **CI/CD:** GitHub Actions  
- **Orchestration:** Kubernetes  
- **Monitoring:** Prometheus, Grafana  
- **Local Cluster:** Minikube  

---

## 📁 Project Structure

```
├── app
│   ├── app.py
│   ├── Dcokerfile
│   └── requirements.txt
├── deployment.yaml
├── k8s
│   └── namespace.yaml
└── service.yaml

2 directories, 6 files
```

---

## ⚙️ Application Details

A simple Flask-based REST API designed for containerized deployment.

### API Endpoints

| Endpoint | Description |
|---------|-------------|
| `/` | Application status and environment |
| `/health` | Health check endpoint |

---

## 🐳 Docker

### Build Image
```bash
docker build -t devops-app ./app
```

### Run Locally
```bash
docker run -p 5000:5000 devops-app
```

---

## 🔁 CI/CD Pipeline

The GitHub Actions pipeline:

1. Triggers on push to `main`
2. Builds Docker image
3. Pushes image to DockerHub

### Required Secrets

- `DOCKER_USERNAME`
- `DOCKER_PASSWORD`

---

## ☸️ Kubernetes Deployment

### Start Cluster
```bash
minikube start
```

### Deploy Resources
```bash
kubectl apply -f k8s/namespace.yaml
kubectl apply -f k8s/
```

### Access Application
```bash
minikube service devops-service -n devops-project
```
