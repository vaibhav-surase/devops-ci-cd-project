🚀 End-to-End Automated DevOps CI/CD Pipeline
This project demonstrates a production-ready CI/CD pipeline. It automates the entire lifecycle of a web application—from code commit and Jenkins orchestration to Docker containerization and Kubernetes deployment.

🛠 Tech Stack
CI/CD: Jenkins (Pipeline-as-Code)

Containerization: Docker

Orchestration: Kubernetes (K8s)

Registry: Docker Hub

Source Control: GitHub

Environment: Linux (Ubuntu/RHEL)

📈 Step-by-Step Implementation
1. Project Structure
The project is organized to support automation. It includes the application code, a Dockerfile for containerization, and Kubernetes manifests for orchestration.

Key Files: app.js, Dockerfile, Jenkinsfile, k8s/deployment.yaml.

  <img width="457" height="212" alt="tree" src="https://github.com/user-attachments/assets/d89e0440-9e80-49fa-a04a-a1a858c9cf2d" />

2. Local Development & Testing
Before automation, the application was tested locally to ensure functional stability.

Bash
docker run -d -p 3000:30007 devops-app
  <img width="1360" height="674" alt="Hello 30007" src="https://github.com/user-attachments/assets/91fa6159-27fb-4b99-8d44-c733dc282606" />
 

3. Docker Image Build
The application is packaged into a lightweight Docker image using a custom Dockerfile.

docker build -t vaibhavsurase/devops-app .
 <img width="526" height="594" alt="Screenshot 2026-04-24 204110" src="https://github.com/user-attachments/assets/e7dcc8c1-74eb-4d60-bb9b-cfba24cdc6c7" />

4. Docker Hub Push
The built image is pushed to a central registry (Docker Hub) to be accessible by the Kubernetes cluster.

docker push vaibhavsurase/devops-app:latest
  <img width="904" height="254" alt="Screenshot 2026-04-24 204515" src="https://github.com/user-attachments/assets/de0ace18-74aa-4e57-bfe3-569e94c1143d" />

5. Kubernetes Infrastructure Deployment
Deployment manifests are applied to the cluster to create the necessary pods and services.

kubectl apply -f k8s/
   <img width="507" height="54" alt="k8s apply" src="https://github.com/user-attachments/assets/bee8de86-7d35-41c3-a23d-5070715f6663" />

6. Pod Management
Two replicas of the application are maintained for high availability.

kubectl get pods
   <img width="637" height="85" alt="k8s pods" src="https://github.com/user-attachments/assets/644310e2-7934-4bd4-bedd-9dec42aa82a5" />

 7. Service Exposure (NodePort)
A Kubernetes Service is configured to expose the application to external traffic using a NodePort.

kubectl get svc
<img width="748" height="84" alt="k8s svc" src="https://github.com/user-attachments/assets/58b69e99-d870-4e8f-b7db-ced94e54727a" />

8. Live Application (Production)
The application is successfully running and accessible via the Kubernetes NodePort.

Access URL: http://<Node-IP>:30007

<img width="1360" height="674" alt="Hello 30007" src="https://github.com/user-attachments/assets/e31d9cee-fdea-49b1-9fe4-d9f369dbf83e" />

9. Jenkins Pipeline Automation
The entire process—Build, Push, and Deploy—is automated through a Jenkins Pipeline.

Build Status: Success (Build #7)

Duration: 1 min 20 sec

<img width="1346" height="716" alt="green stages jenkins" src="https://github.com/user-attachments/assets/d49cb8e9-52e6-48c6-8fcf-ad58ea940b26" />

10. Version Control (GitHub)
The project code and all configuration files are maintained in GitHub for collaboration and tracking.

[Add Screenshot: Your GitHub Repository Homepage]

🛠 Manual Execution (For Reviewers)
Note: This project was designed and built from scratch. To replicate the environment manually, use the following commands:

1. Build the Container:

Bash
docker build -t devops-app .
2. Deploy to Cluster:

Bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
3. Check Status:

Bash
kubectl get all
Developed by: Vaibhav Surase

Role: Application Development & Automation Engineer
