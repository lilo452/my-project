# My Project

Deploy a Python application using Docker, Kubernetes, Helm, and GitHub Actions.

# Links

https://github.com/lilo452/argo-gitops.git
https://github.com/lilo452/Terraform-exam.git

## Project Overview

This project demonstrates a complete containerized application deployment workflow. The application is packaged into a Docker image, stored in a container registry, and deployed to Kubernetes using Helm charts.

The repository includes:

* Python application
* Dockerfile for image creation
* Helm chart for Kubernetes deployment
* GitHub Actions CI/CD pipeline
* Kubernetes manifests managed through Helm

## Prerequisites

Before running this project, ensure you have the following installed:

* Docker 29.x or later
* Kubernetes 1.34.x or later
* Helm 3.x or later
* kubectl configured to communicate with your cluster

## Architecture

This project creates and deploys:

```text
Python Application
        │
        ▼
   Docker Image
        │
        ▼
 Container Registry
        │
        ▼
   Helm Chart
        │
        ▼
 Kubernetes Cluster
```

Components included in the repository:

* Python application (`app.py`)
* Docker image build process
* Helm deployment templates
* Kubernetes Service
* Kubernetes Deployment
* GitHub Actions automation

## Project Structure

```text
my-project/
├── .github/
│   └── workflows/
├── chart/
├── Dockerfile
├── app.py
├── requirements.txt
└── README.md
```

## Development Process

The project was built in the following stages:

### 1. Application Preparation

The Python application and its dependencies were provided by the development team through:

* `app.py`
* `requirements.txt`

### 2. Docker Image Creation

A Dockerfile was created to:

* Install dependencies
* Copy application files
* Expose the application port
* Define the startup command

The image was then built and tested locally before publishing.

### 3. Container Registry Upload

After validating the image locally, it was pushed to Docker Hub for external access and Kubernetes deployment.

### 4. Helm Deployment

The Helm chart was created to manage Kubernetes resources such as:

* Deployment
* Service
* Values configuration
* Ingress (if required)

Using Helm makes deployments repeatable and easier to manage across environments.

### 5. Validation

The application was tested locally and inside Kubernetes to ensure all components worked correctly.

## Running the Project with Docker

### Clone the Repository

```bash
git clone https://github.com/lilo452/my-project.git
cd my-project
```

### Build the Docker Image

```bash
docker build -t <image-name>:<tag> .
```

Example:

```bash
docker build -t my-app:v1 .
```

### Run the Container

```bash
docker run -d -p 8000:8000 --name my-app my-app:v1
```

### Access the Application

Open your browser:

```text
http://localhost:8000
```

## Running the Project with Helm

### Ensure Kubernetes is Running

Verify access to your cluster:

```bash
kubectl get nodes
```

### Install the Helm Chart

```bash
helm install my-app ./chart
```

### Verify Resources

```bash
kubectl get pods
kubectl get svc
```

### Port Forward the Service

```bash
kubectl port-forward service/my-app-svc 8000:80
```

### Access the Application

Open:

```text
http://localhost:8000
```

## CI/CD Pipeline

The repository includes a GitHub Actions workflow for automation.

The pipeline can be extended to:

* Build Docker images
* Run tests
* Push images to Docker Hub
* Deploy to Kubernetes
* Perform Helm upgrades
* moves the helm template result to cd repo


## What I Learned

Throughout this project I gained hands-on experience with:

* Docker image creation
* Container registries
* Kubernetes deployments
* Helm chart development
* CI/CD automation
* GitHub Actions
* Jenkins pipelines


## Future Improvements

* Add Ingress configuration
* Add monitoring with Prometheus and Grafana
* Add automated testing
* Implement Argo CD GitOps deployment
* Add environment-specific Helm values
* Add container security scanning


Created as a DevOps learning project to practice Docker, Kubernetes, Helm, CI/CD, and GitOps workflows.
