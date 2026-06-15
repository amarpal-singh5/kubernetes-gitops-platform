GitOps CI/CD Pipeline with GitHub Actions, ArgoCD & Kubernetes
📌 Overview
This project demonstrates a complete GitOps-based CI/CD pipeline using GitHub Actions, Docker, GitHub Container Registry (GHCR), ArgoCD, and Kubernetes (Kind).
The system follows a Git as the single source of truth model where all application and deployment changes are driven through Git commits.
🏗️ Architecture
High-Level Flow
Developer Push
    ↓
GitHub Repository
    ↓
GitHub Actions (CI)
    ├── Build Docker Image
    ├── Push to GHCR
    ├── Update GitOps Manifest
    └── Commit back to Git
    ↓
GitOps Repository State
    ↓
ArgoCD (Continuous Delivery)
    ↓
Kubernetes Cluster (Kind)
    ↓
Running Application
⚙️ Tech Stack
GitHub Actions (CI Automation)
Docker (Containerization)
GitHub Container Registry (GHCR)
Kubernetes (Kind local cluster)
ArgoCD (GitOps CD controller)
kubectl (cluster management)
🔄 CI/CD Workflow
1. Continuous Integration (GitHub Actions)
On every push to main:
Build Docker image
Tag image with commit SHA
Push image to GHCR
Update Kubernetes deployment manifest
Commit updated manifest back to GitHub
2. Continuous Delivery (ArgoCD)
ArgoCD continuously:
Watches Git repository
Detects changes in gitops/
Compares desired vs live state
Automatically syncs Kubernetes cluster
3. Kubernetes Execution
Runs application as Deployment
Exposes via Service (NodePort)
Performs rolling updates
Maintains desired replica count
🔁 GitOps Self-Healing
If cluster state is modified manually:
kubectl scale deployment github-actions-lab --replicas=1
ArgoCD automatically:
Detects drift
Restores desired state from Git
Scales back to defined replicas
📦 Example Image Flow
ghcr.io/<user>/github-actions-lab:<commit-sha>
Example:
ghcr.io/amarpal-singh5/github-actions-lab:b231df2...
🧠 Key Learnings
GitOps enables declarative infrastructure management
CI and CD are separated by design
Kubernetes continuously reconciles desired state
Image tagging via commit SHA ensures traceability
ArgoCD provides automated drift correction
🚀 Skills Demonstrated
CI/CD pipeline design
GitOps workflow implementation
Kubernetes deployments & services
Docker image lifecycle management
ArgoCD continuous reconciliation
Debugging distributed systems
📁 Project Structure
github-actions-lab/
├── app.py
├── Dockerfile
├── requirements.txt
├── .github/workflows/
│   └── cicd.yml
├── gitops/
│   └── deployment.yaml
├── k8s/
│   └── service.yaml
└── README.md
🔮 Future Enhancements
Multi-environment GitOps (dev/stage/prod)
Helm or Kustomize integration
ArgoCD Image Updater
Canary deployments
Observability (Prometheus + Grafana)
OpenTelemetry tracing
🏁 Summary
This project implements a full end-to-end GitOps CI/CD pipeline where:
Git is the source of truth
CI builds and publishes artifacts
ArgoCD ensures desired state
Kubernetes runs the workload
