# Local Kubernetes Cluster with Minikube

## Objective
This sample project aims to deploy and manage applications in a local Kubernetes cluster using Minikube.

## Tools
- **Minikube**: A tool that makes it easy to run Kubernetes locally.
- **kubectl**: The command-line tool for interacting with Kubernetes clusters.
- **Docker**: A platform for developing, shipping, and running applications in containers.

## Prerequisites
- Install [Minikube](https://minikube.sigs.k8s.io/docs/start/) on your local machine.
- Install [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) for managing Kubernetes clusters.
- Install [Docker](https://docs.docker.com/get-docker/) for containerization.

## Getting Started

### Step 1: Start Minikube
Open your terminal and run the following command to start the Minikube cluster:
```bash
minikube start
```
<p align="center">
  <img align="center" src="D:\Cluser-kubectl\images\minikube_start.png" width="100%">
</p>

### Step 2: Deploy the Application
Since, the .yaml files(aplication.yaml & service.yaml) are already created. Run the following commands to apply the YAML files:
```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

### Step 3: Verify the deployment
Check the status of your pods:
```bash
kubectl get pods
```
### Step 4: Scale Deployments
To scale the deployment to 3 replicas, run:
```bash
kubectl scale deployment/nginx-deployment --replicas=3
```
Verify the scaling:
```bash
kubectl get pods
```

### Step 5: View Deployment Details
To get detailed information about the deployment, run:
```bash
kubectl describe deployment/nginx-deployment
```

### Step 6: Access the Application
To access the Nginx application, run:
```bash
minikube service nginx-service --url
```
