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
