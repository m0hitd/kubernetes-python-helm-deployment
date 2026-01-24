# Python-K8S-Observability-Stack

"A Cloud-Native DevOps capstone project demonstrating container orchestration of a Python Flask microservice using Kubernetes and Helm on a Minikube cluster."

---

## 📌 Project Overview
This project serves as a comprehensive demonstration of modern deployment workflows. By moving away from manual `kubectl` manifests, this project implements a **Helm-based deployment strategy** to automate the lifecycle of a Python application. 

The goal was to build a scalable, repeatable, and configurable infrastructure that mimics a production-grade CI/CD environment.

## 🛠 Tech Stack & Tools
* **Application:** Python 3.9 (Flask)
* **Containerization:** Docker (Multi-stage builds)
* **Orchestration:** Kubernetes (Minikube)
* **Package Management:** Helm (Custom Charts)
* **Automation:** PowerShell / Bash Scripting

---

## 🏗 Key Engineering Features

### 1. Infrastructure as Code (IaC) with Helm
Instead of hard-coded YAML files, this project utilizes **Helm Charts**. 
* **Reusability:** Uses `values.yaml` for environment-specific configurations.
* **Consistency:** Standardizes deployments across Dev, QA, and Prod.
* **Atomic Updates:** Enables easy rollbacks and versioning of the infrastructure.

### 2. Service Discovery & Networking
* **ClusterIP:** Internal communication management.
* **Port-Forwarding:** Bridging the local development environment to the cluster network for real-time testing.

### 3. Resource Management
The deployment is configured with specific resource requests and limits to ensure cluster stability and prevent "noisy neighbor" issues in a shared environment.

---

## 🚀 Getting Started

### Prerequisites
* [Docker Desktop](https://www.docker.com/products/docker-desktop/)
* [Minikube](https://minikube.sigs.k8s.io/docs/start/)
* [Helm](https://helm.sh/docs/intro/install/)

### 1. Initialize the Environment
Start the local cluster using the Docker driver:
```powershell
minikube start --driver=docker

### 2. Deploy via Helm
Navigate to the chart directory and install the release:

powershell
cd my-capstone-chart
helm lint .               # Validate chart syntax
helm install my-project . # Deploy the application
