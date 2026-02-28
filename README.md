# 🚀 End-to-End DevOps CI/CD Project on Microsoft Azure

## 📌 Project Overview
This project demonstrates a complete **end-to-end DevOps CI/CD pipeline** implemented on **Microsoft Azure**.  
The goal of the project is to automate application build, containerization, deployment, and monitoring using modern DevOps tools and cloud-native practices.

Every code change pushed to GitHub is automatically built, containerized, pushed to Azure Container Registry (ACR), and deployed to Azure Kubernetes Service (AKS) using **GitHub Actions**.

---

## 🛠️ Tech Stack
- **Cloud Provider:** Microsoft Azure
- **CI/CD:** GitHub Actions
- **Containerization:** Docker
- **Container Registry:** Azure Container Registry (ACR)
- **Orchestration:** Azure Kubernetes Service (AKS)
- **Infrastructure as Code:** Terraform
- **Monitoring:** Prometheus & Grafana
- **OS:** Ubuntu Linux
- **Version Control:** Git & GitHub

---

## 🏗️ Architecture Overview

**Workflow:**
1. Developer pushes code to GitHub
2. GitHub Actions CI/CD pipeline triggers automatically
3. Docker image is built
4. Image is pushed to Azure Container Registry
5. Kubernetes manifests are applied to AKS
6. Application is exposed using Kubernetes LoadBalancer service
7. Prometheus collects metrics and Grafana visualizes them

GitHub
↓
GitHub Actions (CI/CD)
↓
Docker Build
↓
Azure Container Registry (ACR)
↓
Azure Kubernetes Service (AKS)
↓
LoadBalancer Service
↓
Users / Browser

Monitoring:
AKS → Prometheus → Grafana

---

## 🔄 CI/CD Pipeline Details (GitHub Actions)

The CI/CD pipeline performs the following steps:

1. **Checkout Source Code**
2. **Authenticate with Azure using Service Principal**
3. **Build Docker Image**
4. **Push Docker Image to Azure Container Registry**
5. **Set AKS Context**
6. **Deploy Application to AKS using Kubernetes manifests**

Pipeline is fully automated and requires **no manual intervention**.

---

## 📂 Project Structure
devops-aks-monitoring-project/
│
├── app/
│ ├── app.py
│ └── requirements.txt
│
├── Dockerfile
│
├── k8s/
│ ├── deployment.yaml
│ └── service.yaml
│
├── terraform/
│ ├── main.tf
│ ├── variables.tf
│ └── outputs.tf
│
├── .github/
│ └── workflows/
│ └── ci-cd.yml
│
└── README.md
---

## ☸️ Kubernetes Deployment

- **Deployment**
  - Manages application pods
  - Ensures desired number of replicas
- **Service (LoadBalancer)**
  - Exposes application externally
  - Provides a public IP address

Application becomes accessible through the external IP provided by Azure Load Balancer.

---

## 📊 Monitoring & Observability

- **Prometheus**
  - Collects cluster, node, and pod metrics
- **Grafana**
  - Visualizes metrics using dashboards
  - Monitors CPU, memory usage, pod health, and cluster status

Monitoring stack is deployed inside the AKS cluster.

---

## 🌐 Live Application

Once deployed, the application is accessible via:
http://<AKS-LoadBalancer-External-IP>


---

## 🔐 Security Considerations

- Azure authentication handled via **Service Principal**
- Secrets managed securely using **GitHub Secrets**
- No credentials are hardcoded in the repository

---

## 🧹 Resource Cleanup

To avoid unnecessary cloud costs, all infrastructure can be destroyed using Terraform:

```bash
terraform destroy -auto-approve


🎯 Key Learnings & Outcomes

Designed and implemented a production-style CI/CD pipeline

Gained hands-on experience with AKS, ACR, and Kubernetes

Automated deployments using GitHub Actions

Implemented monitoring and observability

Applied Infrastructure as Code principles using Terraform


📌 Conclusion

This project showcases real-world DevOps practices including automation, container orchestration, cloud infrastructure management, and monitoring.
It reflects practical skills required for DevOps Engineer / Cloud Engineer roles.
