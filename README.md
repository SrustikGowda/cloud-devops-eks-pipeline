# ☁️ Cloud DevOps Pipeline on AWS EKS

A **production-grade CI/CD pipeline** built using GitHub Actions, Terraform, AWS EKS, Helm, and Docker—deploying a Python Flask microservice with observability and monitoring support.

> 🔧 Built for DevOps/SRE interviews, cloud engineering showcase, and real-world infrastructure demos.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![terraform](https://img.shields.io/badge/Terraform-1.7+-blue.svg)](https://www.terraform.io/)
[![kubernetes](https://img.shields.io/badge/Kubernetes-1.29+-326CE5.svg)](https://kubernetes.io/)

---

## 🚀 Project Summary

This project demonstrates a complete cloud-native DevOps setup that includes:

- ✅ GitOps-based CI/CD with GitHub Actions  
- ✅ Infrastructure provisioning with Terraform  
- ✅ Containerized Flask app with Docker  
- ✅ Kubernetes deployment via Helm on EKS  
- ✅ Prometheus + Grafana for observability  
- ✅ Secure and scalable microservice delivery  

---

## 🧱 Stack Overview

| Layer               | Tech Stack                             |
|---------------------|----------------------------------------|
| **Application**     | Python Flask                           |
| **Containerization**| Docker                                 |
| **CI/CD**           | GitHub Actions                         |
| **Infrastructure**  | AWS EKS, Terraform                     |
| **Orchestration**   | Kubernetes, Helm                       |
| **Monitoring**      | Prometheus, Grafana                    |

---

## 📸 Architecture

```mermaid
graph LR
    GitHub[GitHub Repo] -->|Push Event| GitHubActions[GitHub Actions]
    GitHubActions -->|Build/Push| DockerHub[DockerHub Registry]
    GitHubActions -->|Deploy| EKS[AWS EKS Cluster]
    subgraph EKS Cluster
        EKS --> Helm[Helm Deployment]
        Helm -->|Deploys| Flask[Flask App Pods]
        Flask -->|Metrics| Prometheus[Prometheus]
        Prometheus -->|Visualization| Grafana[Grafana]
    end
    Grafana -->|Dashboard| User[End User]
