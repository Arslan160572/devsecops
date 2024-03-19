# Containerized Web Application Stack

Welcome to our containerized web application stack deployment project! This repository contains Infrastructure as Code (IaC) scripts and configuration files for deploying a scalable web application stack consisting of containerized components.

## Components

1. **Web Server:** Containerized HTTP server (e.g., Node.js).
2. **Database Server:** Containerized MySQL or any NoSQL.
3. **Application Server:** Containerized lightweight Python or Node.js application.

## Setup Instructions

1. **Version Control Setup:**
   - Clone this repository: `git clone <repository_url>`
   - Navigate to the project directory: `cd containerized-web-app-stack`

2. **Container Orchestration:**
   - Ensure you have Kubernetes installed.
   - Set up a Kubernetes cluster on AWS EKS.
   - Configure access credentials and permissions:
     - Create an IAM role for EKS cluster.
     - Attach policies allowing access to AWS Secrets Manager.

3. **Build Docker Images:**
   - Build Docker images for each component:
     ```bash
     docker build -t caliberly-web-server-image web_server/
     docker build -t caliberly-database-server-image database/
     docker build -t caliberly-app-server-image application/
     ```

4. **Infrastructure Deployment:**
   - Apply Kubernetes YAML files for deploying the web application stack:
     ```bash
     kubectl apply -f kubernetes/web_server.yaml
     kubectl apply -f kubernetes/database_server.yaml
     kubectl apply -f kubernetes/application_server.yaml
     ```

5. **Secrets Management:**
   - Manage secrets securely using AWS Secrets Manager.
   - Create secrets in AWS Secrets Manager for database credentials.
   - Modify Kubernetes manifests to fetch secrets from AWS Secrets Manager.

6. **Auto-Scaling:**
   - Implement auto-scaling using Horizontal Pod Autoscalers (HPA) based on metrics like CPU utilization or incoming traffic.

## Managing Secrets

For managing secrets securely with AWS Secrets Manager:
- Store sensitive data such as database credentials securely in AWS Secrets Manager.
- Ensure IAM roles and policies are correctly configured to access secrets from Kubernetes pods.
- Modify Kubernetes manifests to fetch secrets from AWS Secrets Manager at runtime.

## Additional Considerations

- Ensure containerization best practices are followed, including Dockerfile optimization and efficient image management.
- Implement proper networking setup for communication between containers and external traffic.
- Use Infrastructure as Code principles for managing container configurations and deployments.
- Document any troubleshooting tips and best practices for maintaining the infrastructure.

For detailed instructions and further information, refer to the individual files and comments in this repository.

