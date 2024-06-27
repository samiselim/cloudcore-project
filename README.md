
# Quiz App

Welcome to the Quiz App repository! This application is designed to provide an interactive quiz experience with a robust backend and a user-friendly frontend.

## Overview

The Quiz App is a full-stack application that allows users to take quizzes on various topics. It includes a frontend built with React.js and a backend built with Node.js. The app is designed to be secure and scalable, utilizing CI/CD pipelines for continuous integration and delivery.

## Features

- User-friendly interface for taking quizzes
- Secure user authentication and authorization
- Real-time quiz scoring
- Detailed reports and analytics
- Continuous integration and deployment with GitHub Actions

## Technologies Used

- **Frontend:** React.js
- **Backend:** Node.js, Express.js
- **CI/CD:** GitHub Actions, Docker, Snyk, Trivy
- **Testing:** Jest, Prettier, ESLint
- **Security:** SonarCloud, Snyk

### Prerequisites

Ensure you have the following installed:

- Node.js (v20.x)
- npm (Node Package Manager)
- Docker

## CI/CD Pipeline

This project uses GitHub Actions for CI/CD. The workflow includes the following jobs:

- **frontend-test:** Linting, testing, and building the frontend.
- **backend-test:** Linting, testing, and building the backend.
- **frontend-security:** Security scanning for the frontend using Snyk.
- **backend-security:** Security scanning for the backend using Snyk.
- **frontend-image:** Building and pushing the frontend Docker image to Docker Hub.
- **backend-image:** Building and pushing the backend Docker image to Docker Hub.
- **k8s-scan:** Scanning Kubernetes manifests for security issues.
- **update-deployments:** Updating Kubernetes deployments with the new images.

## Infrastructure

This application is deployed on an EKS (Elastic Kubernetes Service) cluster and managed using Argo CD. The infrastructure is created and managed using Terraform IaC (Infrastructure as Code). 

### Workflow

1. **Image Scanning:** New images for the frontend and backend are scanned for vulnerabilities using Trivy and Snyk.
2. **Argo CD Deployment:** Argo CD automatically detects changes in the Git repository and updates the EKS deployments with the new images.
3. **Terraform IaC:** Terraform scripts are used to set up and manage the infrastructure, ensuring a consistent and reproducible environment.

## Monitoring

To ensure the application is running smoothly and to monitor its performance, we use Prometheus and Grafana. These tools are installed as pods within the EKS cluster.

- **Prometheus:** Collects and stores metrics from various components of the application.
- **Grafana:** Provides a visual interface to query, visualize, and alert on metrics collected by Prometheus.
