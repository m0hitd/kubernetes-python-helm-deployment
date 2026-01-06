# python-k8s-observability-stack
"A DevOps capstone project demonstrating container orchestration of a Python Flask app using Kubernetes and Helm on a Minikube cluster."

# 🚀 Python Microservice Deployment (Kubernetes & Helm)

This is a DevOps Capstone project demonstrating how to package, deploy, and manage a Python Flask application in a local Kubernetes environment using Helm.

## 📌 Project Overview
The goal of this project was to move away from manual deployments. By creating a custom Helm chart, I automated the process of deploying a microservice, ensuring it is scalable and easily configurable.

## 🛠 Prerequisites
To run this on your local machine, you need the following tools installed:
* [Docker Desktop](https://www.docker.com/products/docker-desktop/)
* [Minikube](https://minikube.sigs.k8s.io/docs/start/)
* [Helm](https://helm.sh/docs/intro/install/)
* [Kubectl](https://kubernetes.io/docs/tasks/tools/)

## 🚀 Getting Started

Run these commands in powershell
### 1. Start the Cluster
First, ensure Docker is running, then start your local Kubernetes cluster:

minikube start
2. Install the Chart
Navigate to the my-capstone-chart folder and install the application using Helm:

PowerShell

cd my-capstone-chart
helm install my-project .
3. Connect to the Application
Because Minikube runs in an isolated environment, you need to "tunnel" the traffic to see the app in your browser:

PowerShell

# Get the pod name
$POD_NAME = (kubectl get pods -l "app.kubernetes.io/name=my-capstone-chart" -o jsonpath="{.items[0].metadata.name}")

# Start the port-forward (Access via http://localhost:8080)
kubectl port-forward $POD_NAME 8080:5000
