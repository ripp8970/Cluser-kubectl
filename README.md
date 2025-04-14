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
  <img align="center" src="https://github.com/ripp8970/Cluser-kubectl/blob/e103afdafd8e2edada4c343a807e557adc600ba4/images/minikube_start.png" width="100%">
</p>

### Step 2: Deploy the Application
Since, the .yaml files(aplication.yaml & service.yaml) are already created. Run the following commands to apply the YAML files:
```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```
<p align="center">
  <img align="center" src="https://github.com/ripp8970/Cluser-kubectl/blob/c607c7fba57250d3374ed91feb4b33d2987a9380/images/apply.png" width="50%">
</p>

### Step 3: Verify the deployment
Check the status of your pods:
```bash
kubectl get pods
```
<p align="center">
  <img align="center" src="https://github.com/ripp8970/Cluser-kubectl/blob/c607c7fba57250d3374ed91feb4b33d2987a9380/images/pods.png" width="50%">
</p>

For detailed view:
```bash
kubectl get pods -o wide
```
<p align="center">
  <img align="center" src="https://github.com/ripp8970/Cluser-kubectl/blob/e83e0ebad566c4798b53fd71a085644d750c5369/images/pods-detailed.png" width="100%">
</p>

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
<p align="center">
  <img align="center" src="https://github.com/ripp8970/Cluser-kubectl/blob/c607c7fba57250d3374ed91feb4b33d2987a9380/images/describe.png" width="50%">
</p>

### Step 6: Access the Application
To access the Nginx application, run:
```bash
minikube service nginx-service --url
```
<p align="center">
  <img align="center" src="https://github.com/ripp8970/Cluser-kubectl/blob/c607c7fba57250d3374ed91feb4b33d2987a9380/images/url.png" width="50%">
</p>

Open the given link in your browser, a page will open:
<p align="center">
  <img align="center" src="https://github.com/ripp8970/Cluser-kubectl/blob/6f27faf8ed1df0e2e03ac5091410341b8d4eade6/images/deploy.png" width="50%">
</p>

## Note:
We can also access the it locally via:
```bash
minikube ssh
```
```bash
curl http://<IP adrees>:80
```

OR

On local machine by the command:
```bash
kubectl port-forward pod/<pod name>(nginx-deployment-96b9d695-24fgn) 8005:80
```
Finally, a cluser was build and deployed locally using Minicube.

### Step 7: Cleaning up
To stop and delete the following Minikube cluser, run the following command:
```bash
minikube stop
minikube delete
```
<p align="center">
  <img align="center" src="https://github.com/ripp8970/Cluser-kubectl/blob/f33bd1e9770b63945fcb7f19f3a9ce3cc5658c18/images/stop.png" width="50%">
</p>