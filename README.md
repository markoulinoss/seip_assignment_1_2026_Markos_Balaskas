# SEIP Assignment 1 – Docker, GitHub Actions, GHCR & Kubernetes

## Prerequisites
- Docker
- Minikube
- kubectl
- Git

## 1. Clone the Repository
```bash
git clone https://github.com/markoulinoss/seip_assignment_1_2026_Markos_Balaskas.git
cd seip_assignment_1_2026_Markos_Balaskas
```

## 2. Start Minikube
```bash
minikube start
```

## 3. Apply Kubernetes Manifests
```bash
kubectl apply -f k8s/
```

This applies all manifests in order:
- `configmap.yaml` - Environment configuration
- `secret.yaml` - Sensitive credentials
- `deployment.yaml` - Application workload (3 replicas)
- `service.yaml` - ClusterIP service

## 4. Verify Pods are Running
```bash
kubectl get pods
```
Wait until all 3 pods show `Running` status.

## 5. Port Forwarding
```bash
kubectl port-forward service/my-service 8080:80
```

## 6. Interact with Endpoints
In a new terminal:
```bash
# Main endpoint
curl http://localhost:8080

# Health check endpoint
curl http://localhost:8080/health
```

## Documentation

The complete assignment report covering Tasks 1–4 is available in the `resources/` directory:

- `resources/resources/seip_assignment_1_2026_Markos_Balaskas.pdf`