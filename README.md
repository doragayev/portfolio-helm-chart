# Portfolio Helm Chart (GitOps Deployment)

This repository manages the Kubernetes deployment of the Portfolio application using Helm and ArgoCD.

## Architecture Overview

Developer
→ Push to App Repository
→ CI (GitHub Actions / Jenkins)
→ Docker Image Build & Push
→ Helm Chart (this repository)
→ ArgoCD Sync
→ Kubernetes Deployment

## Purpose

This repository separates infrastructure from application code and demonstrates:

- Helm-based Kubernetes packaging
- Template-driven deployments
- GitOps workflow using ArgoCD
- Version-controlled infrastructure

## Structure

portfolio/
- Chart.yaml
- values.yaml
- templates/
  - deployment.yaml
  - service.yaml

## Deployment Flow

1. CI builds and pushes Docker image.
2. Helm chart defines how the image is deployed.
3. ArgoCD monitors this repository.
4. On change, ArgoCD syncs and updates Kubernetes.

## Migration Note

This project initially used static Kubernetes manifests.
It was later migrated to a Helm-based GitOps deployment model.

Application Repository:
https://github.com/doragayev/portfolio-devops