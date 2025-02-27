<<<<<<< HEAD
# K8s Stack - Multi Tier Web App

## 📌 Project Overview
This project showcases a cloud-based **ToDo List Application** deployed on **Kubernetes**, integrating **CI/CD automation, security scanning, and cloud infrastructure setup**. The primary focus is on **cloud automation, DevOps pipeline, and Kubernetes orchestration** rather than UI/UX design.

## 🚀 Key Features
- **Containerized Deployment** using Docker and Kubernetes.
- **Automated CI/CD Pipeline** via GitHub Actions.
- **Image Storage & Security** with AWS ECR and Trivy.
- **Ingress Routing & Load Balancing** for efficient network flow.
- **Real-time Database Updates** using MongoDB.
- **IAM Security Policies** for controlled access.
- **Monitoring & Metrics** for performance analysis.

## 🛠️ Tech Stack
- **Cloud Provider**: AWS (EC2, ECR, IAM)
- **Containerization**: Docker
- **Orchestration**: Kubernetes
- **CI/CD**: GitHub Actions
- **Database**: MongoDB
- **Security**: Trivy Scanner, IAM Policies

## 📁 Project Architecture
```plaintext
┌───────────────────────────────┐
│    GitHub Repository         │
└──────────┬───────────────────┘
           ▼
  GitHub Actions (CI/CD Pipeline)
           ▼
     Build Docker Image
           ▼
     Push to AWS ECR
           ▼
 Deploy to Kubernetes Cluster
           ▼
       Ingress Controller
           ▼
       Load Balancer
           ▼
     To-Do App Service
           ▼
      MongoDB Database
```

## 🔧 Setup & Deployment

### 1️⃣ Prerequisites
- AWS Account with IAM permissions
- Kubernetes Cluster (Minikube/EKS)
- Docker & Kubectl installed
- GitHub Actions configured

### 2️⃣ Clone the Repository
```bash
git clone https://github.com/your-repo-name.git
cd your-repo-name
```

### 3️⃣ Build & Push Docker Image
```bash
docker build -t your-ecr-repo-name .
docker tag your-ecr-repo-name:latest <AWS_ACCOUNT_ID>.dkr.ecr.<REGION>.amazonaws.com/your-ecr-repo-name:latest
docker push <AWS_ACCOUNT_ID>.dkr.ecr.<REGION>.amazonaws.com/your-ecr-repo-name:latest
```

### 4️⃣ Deploy to Kubernetes
```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
kubectl apply -f k8s/ingress.yaml
```
![Screenshot 2025-02-15 164028](https://github.com/user-attachments/assets/a31b8198-e7f0-440e-8315-5ce423d6181b)

### 5️⃣ Monitor Application
```bash
kubectl get pods -n your-namespace
kubectl logs -f <pod-name>
```

## 📊 Metrics & Observations
- **System Performance**: Load handling and response times.
- **Database Consistency**: Real-time updates in MongoDB.
- **Network Routing**: Efficient request flow through Ingress & Load Balancer.
- **Security Compliance**: Trivy scans for vulnerabilities.

## 📜 License
This project is open-source and licensed under the **MIT License**.

## 💡 Contributors
- **Sahil Jaroderwala** - Developer & Cloud Engineer
- 
## 📞 Contact
For inquiries, feel free to reach out via email: **sahiljaroder96@**
=======
# #TWSThreeTierAppChallenge

## Overview
This repository hosts the `#TWSThreeTierAppChallenge` for the TWS community. 
The challenge involves deploying a Three-Tier Web Application using ReactJS, NodeJS, and MongoDB, with deployment on AWS EKS. Participants are encouraged to deploy the application, add creative enhancements, and submit a Pull Request (PR). Merged PRs will earn exciting prizes!

**Get The Challenge here**

[![YouTube Video](https://img.youtube.com/vi/tvWQRTbMS1g/maxresdefault.jpg)](https://youtu.be/tvWQRTbMS1g?si=eki-boMemxr4PU7-)

## Prerequisites
- Basic knowledge of Docker, and AWS services.
- An AWS account with necessary permissions.

## Challenge Steps
- [Application Code](#application-code)
- [Jenkins Pipeline Code](#jenkins-pipeline-code)
- [Jenkins Server Terraform](#jenkins-server-terraform)
- [Kubernetes Manifests Files](#kubernetes-manifests-files)
- [Project Details](#project-details)

## Application Code
The `Application-Code` directory contains the source code for the Three-Tier Web Application. Dive into this directory to explore the frontend and backend implementations.

## Jenkins Pipeline Code
In the `Jenkins-Pipeline-Code` directory, you'll find Jenkins pipeline scripts. These scripts automate the CI/CD process, ensuring smooth integration and deployment of your application.

## Jenkins Server Terraform
Explore the `Jenkins-Server-TF` directory to find Terraform scripts for setting up the Jenkins Server on AWS. These scripts simplify the infrastructure provisioning process.

## Kubernetes Manifests Files
The `Kubernetes-Manifests-Files` directory holds Kubernetes manifests for deploying your application on AWS EKS. Understand and customize these files to suit your project needs.

## Project Details
🛠️ **Tools Explored:**
- Terraform & AWS CLI for AWS infrastructure
- Jenkins, Sonarqube, Terraform, Kubectl, and more for CI/CD setup
- Helm, Prometheus, and Grafana for Monitoring
- ArgoCD for GitOps practices

🚢 **High-Level Overview:**
- IAM User setup & Terraform magic on AWS
- Jenkins deployment with AWS integration
- EKS Cluster creation & Load Balancer configuration
- Private ECR repositories for secure image management
- Helm charts for efficient monitoring setup
- GitOps with ArgoCD - the cherry on top!

📈 **The journey covered everything from setting up tools to deploying a Three-Tier app, ensuring data persistence, and implementing CI/CD pipelines.**

## Getting Started
To get started with this project, refer to our [comprehensive guide](https://amanpathakdevops.medium.com/advanced-end-to-end-devsecops-kubernetes-three-tier-project-using-aws-eks-argocd-prometheus-fbbfdb956d1a) that walks you through IAM user setup, infrastructure provisioning, CI/CD pipeline configuration, EKS cluster creation, and more.

### Step 1: IAM Configuration
- Create a user `eks-admin` with `AdministratorAccess`.
- Generate Security Credentials: Access Key and Secret Access Key.

### Step 2: EC2 Setup
- Launch an Ubuntu instance in your favourite region (eg. region `us-west-2`).
- SSH into the instance from your local machine.

### Step 3: Install AWS CLI v2
``` shell
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
sudo apt install unzip
unzip awscliv2.zip
sudo ./aws/install -i /usr/local/aws-cli -b /usr/local/bin --update
aws configure
```

### Step 4: Install Docker
``` shell
sudo apt-get update
sudo apt install docker.io
docker ps
sudo chown $USER /var/run/docker.sock
```

### Step 5: Install kubectl
``` shell
curl -o kubectl https://amazon-eks.s3.us-west-2.amazonaws.com/1.19.6/2021-01-05/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin
kubectl version --short --client
```

### Step 6: Install eksctl
``` shell
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
sudo mv /tmp/eksctl /usr/local/bin
eksctl version
```

### Step 7: Setup EKS Cluster
``` shell
eksctl create cluster --name three-tier-cluster --region us-west-2 --node-type t2.medium --nodes-min 2 --nodes-max 2
aws eks update-kubeconfig --region us-west-2 --name three-tier-cluster
kubectl get nodes
```

### Step 8: Run Manifests
``` shell
kubectl create namespace workshop
kubectl apply -f .
kubectl delete -f .
```

### Step 9: Install AWS Load Balancer
``` shell
curl -O https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.5.4/docs/install/iam_policy.json
aws iam create-policy --policy-name AWSLoadBalancerControllerIAMPolicy --policy-document file://iam_policy.json
eksctl utils associate-iam-oidc-provider --region=us-west-2 --cluster=three-tier-cluster --approve
eksctl create iamserviceaccount --cluster=three-tier-cluster --namespace=kube-system --name=aws-load-balancer-controller --role-name AmazonEKSLoadBalancerControllerRole --attach-policy-arn=arn:aws:iam::626072240565:policy/AWSLoadBalancerControllerIAMPolicy --approve --region=us-west-2
```

### Step 10: Deploy AWS Load Balancer Controller
``` shell
sudo snap install helm --classic
helm repo add eks https://aws.github.io/eks-charts
helm repo update eks
helm install aws-load-balancer-controller eks/aws-load-balancer-controller -n kube-system --set clusterName=my-cluster --set serviceAccount.create=false --set serviceAccount.name=aws-load-balancer-controller
kubectl get deployment -n kube-system aws-load-balancer-controller
kubectl apply -f full_stack_lb.yaml
```

### Cleanup
- To delete the EKS cluster:
``` shell
eksctl delete cluster --name three-tier-cluster --region us-west-2
```
- To clean up rest of the stuff and not incure any cost
```
Stop or Terminate the EC2 instance created in step 2.
Delete the Load Balancer created in step 9 and 10.
Go to EC2 console, access security group section and delete security groups created in previous steps
```

## Contribution Guidelines
- Fork the repository and create your feature branch.
- Deploy the application, adding your creative enhancements.
- Ensure your code adheres to the project's style and contribution guidelines.
- Submit a Pull Request with a detailed description of your changes.

## Rewards
- Successful PR merges will be eligible for exciting prizes!

## Support
For any queries or issues, please open an issue in the repository.

---
Happy Learning! 🚀👨‍💻👩‍💻
>>>>>>> 1b5af7a (Initial commit from copied repo)
