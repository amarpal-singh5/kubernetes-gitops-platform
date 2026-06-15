GitOps CI/CD Pipeline with GitHub Actions, ArgoCD & Kubernetes
📌 Overview
This project demonstrates a complete GitOps-based CI/CD pipeline using:
GitHub Actions (CI automation)
Docker + GitHub Container Registry (GHCR)
ArgoCD (GitOps continuous delivery)
Kubernetes (Kind local cluster)
The system follows a Git as the single source of truth model where all deployments are driven through Git commits.

🏗️ Architecture
CI/CD + GitOps Flow
Developer Push
      ↓
GitHub Repository
      ↓
GitHub Actions (CI)
  - Build Docker Image
  - Push to GHCR
  - Update GitOps Manifest
  - Commit back to Git
      ↓
Git Repository (GitOps State)
      ↓
ArgoCD (CD Controller)
      ↓
Kubernetes Cluster (Kind)
      ↓
Running Application

