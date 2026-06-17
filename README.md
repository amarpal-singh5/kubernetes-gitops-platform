# GitOps CI/CD Platform with GitHub Actions, ArgoCD & Kubernetes

A production-style CI/CD and GitOps pipeline that automates building, containerizing, and deploying a Python application to Kubernetes using GitHub Actions, GitHub Container Registry (GHCR), and ArgoCD.

This project demonstrates a complete end-to-end software delivery workflow used in modern platform engineering environments.

---

## 🧭 Architecture Overview

```text
Developer
   ↓
GitHub (Source Code)
   ↓
GitHub Actions (CI Pipeline)
   ↓
GHCR (Container Registry)
   ↓
ArgoCD (GitOps Controller)
   ↓
Kubernetes Cluster

