# Kubernetes Manifests — Banking App

![Kubernetes](https://img.shields.io/badge/Kubernetes-1.31-blue)
![ArgoCD](https://img.shields.io/badge/GitOps-ArgoCD-orange)

## Overview
Kubernetes manifests for deploying the three-tier banking application on AWS EKS using GitOps principles with Argo CD.

## Structure
├── namespace.yml          # Banking app namespace
├── frontend/
│   ├── deployment.yml     # Frontend deployment (2 replicas)
│   └── service.yml        # LoadBalancer service
├── backend/
│   ├── deployment.yml     # Backend deployment (2 replicas)
│   ├── service.yml        # ClusterIP service
│   └── configmap.yml      # App configuration
└── database/
└── secret.yml         # Database credentials

## GitOps with Argo CD
This repository is connected to Argo CD which:
- Automatically detects changes pushed to main branch
- Deploys updates to EKS cluster automatically
- Maintains desired state and prevents drift
- Self-heals if manual changes are detected

## Deployments
| Component | Replicas | Image |
|---|---|---|
| Frontend | 2 | ECR faustina-frontend:latest |
| Backend | 2 | ECR faustina-backend:latest |

## Author
**Faustina Nwokolo** — Cloud & DevOps Engineer