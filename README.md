# Nginx on Kubernetes (Minikube)

My MLOps Assignment 3 project. I deployed an nginx Pod on a local
Minikube cluster and exposed it using a NodePort Service.

## Environment
- Ubuntu on WSL 2, Docker Desktop
- kubectl v1.37.2, Kubernetes v1.37.0, Minikube

## Project structure
```
k8s-nginx-project/
├── app.yml
├── service.yml
├── requirements.txt
└── README.md
```

## Deployment
```bash
kubectl apply -f app.yml
kubectl apply -f service.yml
```

## Verify
```bash
kubectl get pods
kubectl get svc
```

## Access
```bash
kubectl port-forward pod/nginx-pod 8080:80
```
Then open http://localhost:8080

## Cleanup
```bash
kubectl delete -f service.yml
kubectl delete -f app.yml
```

## Problems I faced
- Docker command was not found in WSL, fixed by enabling WSL integration in Docker Desktop.

Author: RAJAEHTASHAM
