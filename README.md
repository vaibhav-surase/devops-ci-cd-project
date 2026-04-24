End-to-End Automated DevOps CI/CD Pipeline
This project demonstrates a production-grade CI/CD pipeline, automating the journey from a local Node.js application to a high-availability Kubernetes cluster.

Tech Stack
Source Control: GitHub

CI/CD: Jenkins (Pipeline-as-Code)

Containerization: Docker

Registry: Docker Hub

Orchestration: Kubernetes (kubeadm Cluster)

Environment: Linux (Ubuntu/RHEL)

Step-by-Step Implementation

STEP 1: Project Initialization & Structure
The project was initialized with a specialized directory structure, including the application logic (app.js), dependency management (package.json), and automation scripts (Dockerfile, Jenkinsfile).
Proves: Repository initialized with all required configuration files.

<img width="1347" height="576" alt="git Repo" src="https://github.com/user-attachments/assets/e3032655-e040-47cb-86e0-caca198ba459"/>



STEP 2: Application Development & Local Testing
I developed a Node.js server and verified its functionality locally within a Docker container to ensure the "Hello This Is My CI/CD DevOps Project🚀" response was active.

docker build -t devops-app .

docker run -d -p 3000:3000 devops-app
Proves: Application logic is stable and serving traffic on Port 3000.

<img width="1360" height="139" alt="docker 3000" src="https://github.com/user-attachments/assets/d92f07ef-ea21-4a62-ac22-0de6eb244e0d"/>


STEP 3: Docker Hub Registry Integration
To enable cluster-wide access, the local image was tagged and pushed to Docker Hub. This acts as our centralized image repository.

docker tag devops-app vaibhavsurase/devops-app
docker push vaibhavsurase/devops-app

Proves: Container image successfully versioned and hosted on Docker Hub.

<img width="904" height="254" alt="Screenshot 2026-04-24 204515" src="https://github.com/user-attachments/assets/7a54d36b-cd26-4964-944b-419e7e43da60"/>


STEP 4: Kubernetes Infrastructure (IaC)
I authored Kubernetes manifests (deployment.yaml and service.yaml) to define a desired state of 2 replicas and a NodePort service.

kubectl apply -f k8s/

Proves: Infrastructure-as-Code applied successfully to the cluster.

<img width="507" height="54" alt="k8s apply" src="https://github.com/user-attachments/assets/d20ce184-ebd8-4f51-9b18-ce3e7bedfb90"/>


 STEP 5: Cluster Verification (Pods & Services)
After deployment, I verified that the Kubernetes control plane successfully scheduled the pods and mapped the service ports.

kubectl get pods
kubectl get svc

Proves: 2 Pods are 'Running' and the service is exposed on NodePort 30007.

<img width="637" height="85" alt="k8s pods" src="https://github.com/user-attachments/assets/b4ce3246-f858-4fed-a90b-d2a7e77c5d4b"/>
<img width="748" height="84" alt="k8s svc" src="https://github.com/user-attachments/assets/7901e6d5-2e6e-48bd-a4c8-f912ddbe56dd"/>


STEP 6: Final Production Validation
The end goal: accessing the application via the Kubernetes NodePort.

Production URL: http://<NODE-IP>:30007

Proves: End-to-end success—app is live on the K8s cluster.

<img width="1360" height="674" alt="Hello 30007" src="https://github.com/user-attachments/assets/5b6f6f87-d9eb-4d1a-86fc-93e272d8ee7c"/>



STEP 7: Jenkins Pipeline Configuration
Jenkins was linked to the GitHub SCM to listen for code changes and trigger the automated workflow.

Proves: Jenkins is correctly tracking the GitHub repository.

<img width="1346" height="667" alt="SCM" src="https://github.com/user-attachments/assets/85ea3a99-519e-46a6-a7dc-a7b52f2c029d"/>


STEP 8: Pipeline Success & Results
The final automated run (Build #7) was completed successfully, demonstrating a stable and repeatable delivery process.

Duration: ~1 min 20 sec

Proves: CI/CD Pipeline status is Green (Success ✅).


<img width="1346" height="716" alt="green stages jenkins" src="https://github.com/user-attachments/assets/e922758b-3e8a-43f5-aa3f-c7850498aa0d"/>



🛠 Manual Setup Instructions
To reproduce this project, follow these commands:

Build Container: docker build -t devops-app .

Deploy to K8s: kubectl apply -f k8s/

Verify: kubectl get all

Developed by: Vaibhav Surase

Role: Application Development & Automation Engineer
