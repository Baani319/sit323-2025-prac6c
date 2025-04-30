# SIT323-2025-Prac6C - Kubernetes Deployment Task

This repository contains the source code and configuration files for deploying a simple Node.js application on a Kubernetes cluster using Minikube.

## 🔧 Tools and Technologies

- **Node.js**: JavaScript runtime for the application.
- **Docker**: Containerizing the Node.js application.
- **Kubernetes (Minikube)**: Orchestration of the app in a local Kubernetes cluster.
- **Kubectl**: Command-line tool to interact with Kubernetes.
- **Git & GitHub**: Version control and project hosting.

## 📁 Project Structure

sit323-2025-prac6c/ │ ├── Dockerfile # Docker image build configuration ├── deployment.yaml # Kubernetes Deployment configuration ├── service.yaml # Kubernetes Service configuration ├── app.js # Simple Node.js application (example) ├── package.json # Node.js project configuration ├── README.md # This file

shell
Copy code

## 🚀 Steps to Run Locally

### 1. Start Minikube

Make sure Minikube is installed and running:

```bash
minikube start
2. Set Docker Environment for Minikube
Set the environment to use Minikube’s Docker daemon:

bash
Copy code
@FOR /f "tokens=*" %i IN ('minikube -p minikube docker-env --shell cmd') DO @%i
3. Build Docker Image
Build the Docker image for your application:

bash
Copy code
docker build -t sit323-k8s-app .
4. Deploy to Kubernetes
Deploy your application and service to the Kubernetes cluster:

bash
Copy code
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
5. Verify the Application
Check the status of your pods and services:

bash
Copy code
kubectl get pods
kubectl get services
6. Forward Port to Access the Application
Forward the port from the Kubernetes service to your local machine:

bash
Copy code
kubectl port-forward service/sit323-k8s-service 3000:3000
Now, open your browser and visit http://localhost:3000 to access the application.
