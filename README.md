# Docker Kubernetes Orchestration

## Description
This project involves containerizing a 3-tier MERN (MongoDB, Express, React, Node.js) web application. It covers Docker-based containerization, Docker Compose orchestration, and Kubernetes deployment. The goal is to ensure the scalability and flexibility of the application while adhering to best practices in containerization and cloud-native development.

## Project Structure
The repository consists of multiple branches, each representing different parts of the project:

- **main**: Contains the core application and configurations.
- **Docker**: Handles Docker containerization for MongoDB, backend, and frontend.
- **Docker_Compose**: Includes Docker Compose configurations to orchestrate multi-container deployments.
- **Docker_Compose_Registry**: Implements a private Docker image registry for storing and retrieving container images.
- **Kubernetes**: Contains Kubernetes manifests for deploying the application on a Kubernetes cluster.
- **Kubernetes_Operator**: Implements MongoDB as a Kubernetes Operator for managing database clusters.

## Technologies Used
- **Docker**: To containerize the frontend, backend, and MongoDB services.
- **Docker Compose**: For orchestrating multi-container environments.
- **Kubernetes**: To manage the deployment, scaling, and networking of the containers.
- **MongoDB Kubernetes Operator**: For automating the management of MongoDB databases in Kubernetes clusters.
- **Prometheus/Grafana & EFK stack**: For monitoring and logging the application.
- **Helm & Skaffold**: For managing Kubernetes applications and automating deployments.
- **GitOps**: Using tools like ArgoCD or Flux to manage Kubernetes resources through Git.

## Setup and Installation

### Prerequisites
Ensure you have the following installed:
- Docker
- Docker Compose
- Kubernetes (Minikube or another local cluster)
- Helm (for package management in Kubernetes)
- Skaffold (for automating builds and deployments)
- Prometheus & Grafana (for monitoring)
- EFK Stack (Elasticsearch, Fluentd, Kibana for logging)

### How to Run

1. **Docker Setup:**
    - Build and run the MongoDB container:
      ```bash
      docker run -d --name mongodb-service -v mongodb-volume:/data/db mongo
      ```
    - Build and run the backend and frontend containers using their respective `Dockerfile`.

2. **Docker Compose:**
    - Create and configure the `docker-compose.yaml` to orchestrate the backend, frontend, and MongoDB services.
    - Run the services:
      ```bash
      docker-compose up
      ```

3. **Kubernetes Deployment:**
    - Deploy the application on a Kubernetes cluster using the YAML manifests provided in the `Kubernetes` branch.
    - Use `kubectl apply -f <manifest.yaml>` to apply the Kubernetes configuration files.

4. **Private Docker Registry:**
    - Set up a private Docker image registry, and push your container images into it. Redeploy using images from the private registry.

5. **Kubernetes Operator:**
    - Deploy the MongoDB Operator to manage the database cluster using Kubernetes.

6. **Monitoring & Logging:**
    - Set up Prometheus and Grafana for monitoring.
    - Set up the EFK stack (Elasticsearch, Fluentd, Kibana) for logging.

7. **Helm Charts & Skaffold:**
    - Use Helm to deploy the application via charts.
    - Use Skaffold for automated build and deployment of your application.

8. **GitOps Deployment:**
    - Deploy the application using GitOps concepts via ArgoCD or Flux.

## Features
- Full Docker-based containerization of a MERN stack application.
- Docker Compose for multi-container orchestration.
- Kubernetes-based scaling and orchestration.
- MongoDB deployment via Kubernetes Operator.
- Continuous Monitoring and Logging with Prometheus, Grafana, and the EFK stack.
- GitOps automation with Flux/ArgoCD.
- Skaffold for continuous development with automated builds.

## Best Practices Followed
- Utilized multi-stage Docker builds to reduce image size.
- Used `.dockerignore` to exclude unnecessary files from Docker images.
- Implemented non-root users in containers for better security.
- Configured Liveness, Readiness, and Startup Probes in Kubernetes for improved resilience.
- Created Helm charts for reusable Kubernetes deployments.
- Employed GitOps for efficient, version-controlled deployments.

## Repository Structure
- **frontend/**: React-based frontend source code.
- **backend/**: Node.js-based backend source code.
- **k8s/**: Kubernetes manifest files for deploying the MERN application.
- **Dockerfile**: Dockerfile to containerize the backend and frontend applications.
- **docker-compose.yaml**: Docker Compose file to orchestrate MongoDB, backend, and frontend containers.

## Author
- **Adnane El Bouhali**  

## License
This project is licensed under the MIT License.
