
# Quiz App

Welcome to the Quiz App repository! This application is designed to provide an interactive quiz experience with a robust backend and a user-friendly frontend.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Running the Application](#running-the-application)
- [CI/CD Pipeline](#cicd-pipeline)
- [Infrastructure](#infrastructure)
- [Contributing](#contributing)
- [License](#license)

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

## Getting Started

To get a local copy up and running, follow these steps.

### Prerequisites

Ensure you have the following installed:

- Node.js (v20.x)
- npm (Node Package Manager)
- Docker

### Installation

1. **Clone the repository:**

   You can download the repository by clicking [here](https://github.com/your-username/quiz-app/archive/refs/heads/main.zip).

2. **Install dependencies:**

   After downloading, extract the zip file and navigate to the project directory to install the necessary dependencies for both the frontend and backend.

## Running the Application

### Running the Frontend

Navigate to the frontend directory and start the development server.

### Running the Backend

Navigate to the backend directory and start the backend server.

The application should now be running on `http://localhost:3000` for the frontend and `http://localhost:5000` for the backend.

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

### Key Components

- **EKS Cluster:** The application runs on an Amazon EKS cluster, providing scalability and high availability.
- **Argo CD:** Continuous deployment tool for Kubernetes. It monitors the Git repository for changes in the Kubernetes manifests and updates the EKS deployments with the new images.
- **Terraform:** Infrastructure as Code tool used to provision and manage the EKS cluster and related resources.

### Workflow

1. **Image Scanning:** New images for the frontend and backend are scanned for vulnerabilities using Trivy and Snyk.
2. **Argo CD Deployment:** Argo CD automatically detects changes in the Git repository and updates the EKS deployments with the new images.
3. **Terraform IaC:** Terraform scripts are used to set up and manage the infrastructure, ensuring a consistent and reproducible environment.

## Contributing

We welcome contributions to improve the Quiz App. Please fork the repository and create a pull request with your changes.

1. Fork the Project
2. Create your Feature Branch
3. Commit your Changes
4. Push to the Branch
5. Open a Pull Request

## License

Distributed under the MIT License. See `LICENSE` for more information.
