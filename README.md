# DevOps CI/CD Pipeline for Containerized Two-Tier Flask Application

## Overview

This project demonstrates the deployment of a containerized two-tier web application using **Flask** and **MySQL** on **AWS EC2**. The application is containerized with Docker, orchestrated using Docker Compose, and deployed automatically through a Jenkins CI/CD pipeline integrated with GitHub.

The project showcases essential DevOps concepts such as containerization, continuous integration, continuous deployment, Docker networking, persistent storage, and cloud deployment.

---

## Architecture

```
                +------------------+
                |      GitHub      |
                +--------+---------+
                         |
                    Git Push
                         |
                         v
                +------------------+
                |     Jenkins      |
                |   CI/CD Pipeline |
                +--------+---------+
                         |
          Build Docker Images & Deploy
                         |
                         v
              +----------------------+
              |     Docker Compose   |
              +----------+-----------+
                         |
          +--------------+---------------+
          |                              |
          v                              v
+---------------------+        +----------------------+
|   Flask Container   | <----> |   MySQL Container    |
+---------------------+        +----------------------+
               |
               v
        AWS EC2 Instance
```

---

## Features

- Containerized Flask web application
- MySQL database running in a separate Docker container
- Docker Compose for multi-container orchestration
- Jenkins CI/CD pipeline for automated deployment
- GitHub integration for source code management
- Persistent Docker volumes for database storage
- Docker networking for secure inter-container communication
- Deployment on AWS EC2

---

## Tech Stack

- AWS EC2
- Docker
- Docker Compose
- Jenkins
- Git & GitHub
- Flask
- Python
- MySQL
- Linux (Ubuntu)

---

## Project Structure

```
.
├── app.py
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
├── Jenkinsfile
├── templates/
├── static/
└── README.md
```

---

## Prerequisites

- AWS EC2 (Ubuntu)
- Docker
- Docker Compose
- Jenkins
- Git
- GitHub Account

---

## Installation

### Clone the Repository

```bash
git clone https://github.com/<your-username>/<repository-name>.git

cd <repository-name>
```

---

### Build and Run using Docker Compose

```bash
docker compose up -d --build
```

Check running containers

```bash
docker ps
```

Stop containers

```bash
docker compose down
```

---

## Jenkins CI/CD Pipeline

The Jenkins pipeline performs the following stages:

1. Clone source code from GitHub
2. Build Docker image
3. Stop existing containers
4. Deploy updated containers using Docker Compose
5. Verify successful deployment

---

## Docker Components

### Flask Container

- Hosts the web application
- Connects to MySQL container
- Exposes application on port 5000

### MySQL Container

- Stores application data
- Uses Docker volumes for persistent storage

---

## Networking

Docker Compose automatically creates a dedicated bridge network allowing the Flask container to communicate securely with the MySQL container using the service name.

---

## Persistent Storage

A Docker volume is configured to preserve MySQL data even after container recreation.

---

## CI/CD Workflow

```
Developer
    │
    ▼
GitHub Repository
    │
    ▼
Jenkins Pipeline
    │
    ├── Clone Repository
    ├── Build Docker Image
    ├── Deploy Containers
    ▼
Docker Compose
    │
    ├── Flask Container
    └── MySQL Container
```

---

## Skills Demonstrated

- AWS EC2
- Docker
- Docker Compose
- Jenkins
- CI/CD
- Git & GitHub
- Flask
- MySQL
- Linux Administration
- Docker Networking
- Docker Volumes

---

## Future Enhancements

- Deploy Docker images to Amazon ECR
- Kubernetes deployment using Amazon EKS
- Terraform for Infrastructure as Code
- GitHub Webhooks for automatic pipeline triggers
- Nginx Reverse Proxy
- HTTPS with SSL/TLS
- Prometheus and Grafana monitoring
- AWS Secrets Manager integration

---

## Author

**Subbiah R**

- LinkedIn: https://www.linkedin.com/in/subbiah-ramasamy-b090a125b/
- GitHub: https://github.com/subbiahramu
