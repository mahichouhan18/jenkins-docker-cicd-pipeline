# Jenkins + Docker CI/CD Pipeline

A hands-on project demonstrating how to use Jenkins and Docker to build and deploy a simple web application in a local lab environment.

## Overview

This project uses a Jenkins Pipeline to check out source code from GitHub, build a Docker image, and run the application inside a Docker container.

## Technologies Used

- Jenkins
- Docker
- Git and GitHub
- Jenkins Pipeline
- HTML
- Windows-based Jenkins agent (`bat` commands)

## Project Structure

```text
jenkins-docker-cicd-pipeline/
├── Dockerfile
├── Jenkinsfile
├── index.html
└── README.md
```

## Pipeline Stages

1. **Checkout:** Retrieves the source code from the `main` branch of this GitHub repository.
2. **Build Docker Image:** Builds a Docker image named `jenkins-docker-cicd`.
3. **Deploy Container:** Removes the previous container named `jenkins-cicd-app`, if present, and starts a new container.

## Port Mapping

The container uses port `80`, mapped to port `8081` on the host.

After a successful deployment, open:

http://localhost:8081

## Prerequisites

- Jenkins installed and running
- Git available to Jenkins
- Docker installed and running
- A Jenkins agent configured to execute Windows `bat` commands
- Permissions for the Jenkins agent to run Docker commands

## How to Run

1. Clone this repository or configure Jenkins to check it out from GitHub.
2. Ensure Docker Desktop or the Docker Engine is running.
3. Create a Jenkins Pipeline job and configure the pipeline to use this repository's `Jenkinsfile`.
4. Run the Jenkins job.
5. Review the console output and confirm that all pipeline stages succeed.
6. Open `http://localhost:8081` to check the deployed web application.

## Verification

Check whether the container is running:

```bat
docker ps
```

Check the application container logs:

```bat
docker logs jenkins-cicd-app
```

## Troubleshooting

- **Docker command fails:** Verify that Docker is running and accessible to the Jenkins agent.
- **Port conflict:** Ensure host port `8081` is available.
- **Container does not start:** Review the Jenkins console output and container logs.
- **Application does not load:** Confirm that the container is running and that the Dockerfile serves the application on port `80`.

## Learning Outcomes

- Writing a basic Jenkins Pipeline
- Checking out source code from GitHub
- Building Docker images
- Running and replacing Docker containers
- Troubleshooting a local CI/CD workflow

## Environment

This project is intended for learning and local lab practice. It does not claim production deployment or production-grade CI/CD implementation.
