# Small DevOps Project with Kubernetes & Minikube

This repo demonstrates a simple DevOps workflow:
- Dockerized web application (Flask)
- CI/CD pipeline with GitHub Actions
- Kubernetes deployment on Minikube

## Quick Start

### 1. Build and Run Locally
```bash
docker build -t devops-demo .
docker run -p 5000:5000 devops-demo
```

### 2. Run on Minikube
```bash
minikube start
eval $(minikube docker-env)
docker build -t devops-demo .
kubectl apply -f k8s/
minikube service devops-demo-service
```

### 3. Push changes to GitHub to trigger CI/CD

## Directory Structure

- `app/` - Flask app
- `Dockerfile` - Container config
- `.github/workflows/ci-cd.yml` - CI/CD pipeline
- `k8s/` - Kubernetes manifests (deployment, service)
