# End-to-End DevOps Project

## Tools Used
- Git, GitHub
- Jenkins
- Docker
- Kubernetes with Helm Charts
- AWS (EKS assumed)
- Monitoring: Prometheus and Grafana

## Manual Setup Instructions

### Prerequisites
- AWS CLI configured
- kubectl installed
- Docker & Jenkins installed
- EKS cluster created and kubeconfig setup

### Steps

1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   ```

2. Build and push Docker image:
   ```bash
   cd app
   docker build -t <your-dockerhub-username>/devops-app:latest .
   docker push <your-dockerhub-username>/devops-app:latest
   ```

3. Deploy using Helm:
   ```bash
   cd helm
   helm install devops-app .
   ```

4. Configure Prometheus and Grafana using files in the `monitoring` folder.

5. Jenkins Pipeline:
   - Use the `Jenkinsfile` in a multibranch pipeline job.
   - Ensure Jenkins has access to Docker and kubectl.

## Output
A complete CI/CD pipeline from GitHub to Kubernetes with monitoring in place.
