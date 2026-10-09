# Task 12: Kubernetes Cluster Setup and Deployment

## Overview
This project demonstrates the setup of a local Kubernetes cluster using Minikube and Docker. A containerized Nginx web application is deployed using Kubernetes YAML manifests. The deployment is verified by checking pod status, service configuration, browser output, and scaling operations.

## Objectives
- Set up a local Kubernetes cluster using Minikube.
- Create Kubernetes Deployment and Service YAML files.
- Deploy a sample Nginx container.
- Verify pod, deployment, and service operations.
- Monitor deployment status and test scaling.

## Tools and Technologies
- Kubernetes
- Minikube
- Docker Desktop
- kubectl
- Visual Studio Code
- Windows PowerShell
- Nginx

## Project Structure
```text
Task-12-Kubernetes/
├── deployment.yaml
├── service.yaml
├── screenshots/
└── LT_Task_12_Kubernetes_Cluster_Setup_and_Deployment_Report.pdf
```

## Implementation

### 1. Start the Kubernetes Cluster
```powershell
minikube start --driver=docker
```

### 2. Check Cluster Status
```powershell
minikube status
kubectl get nodes
kubectl get pods -A
```

### 3. Deploy the Application
```powershell
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

### 4. Verify Deployment and Service
```powershell
kubectl get deployments
kubectl get pods
kubectl get services
```

### 5. Access the Nginx Application
```powershell
kubectl port-forward service/nginx-service 8080:80
```

Open the following URL in a browser:

`http://localhost:8080`

The default Nginx welcome page confirms that the web server is responding through the Kubernetes Service.

### 6. Test Scaling
Scale the deployment to three replicas:

```powershell
kubectl scale deployment nginx-deployment --replicas=3
kubectl get pods
```

Restore the original replica count:

```powershell
kubectl scale deployment nginx-deployment --replicas=2
kubectl get pods
```

## Results
- The Minikube cluster was started successfully.
- The Kubernetes node was verified as Ready.
- The Nginx Deployment maintained two running pods.
- The Nginx Service was configured using NodePort 30080.
- The Nginx welcome page was accessed in the browser.
- Scaling to three replicas was tested, followed by restoration to two replicas.

## Files Included
- `deployment.yaml` — Kubernetes Deployment configuration.
- `service.yaml` — Kubernetes Service configuration.
- `screenshots/` — Implementation and verification screenshots, if included.
- `LT_Task_12_Kubernetes_Cluster_Setup_and_Deployment_Report.pdf` — Detailed practical report.

## Conclusion
This task demonstrates the basic Kubernetes orchestration workflow using Minikube, Docker, Deployment and Service manifests. The application was deployed, verified through kubectl commands and browser access, and tested for scaling.

## Author
Sagar Sunil Chandratre
