<a id="readme-top"></a>

<!-- PROJECT SHIELDS -->
<!--
*** Reference-style links for badges.
*** Adjust at bottom of file if URLs change.
-->

<!-- PROJECT LOGO -->
<div align="center">

<h3 align="center">DevOps Portfolio Pipeline — Local k3s Deployment</h3>

  <p align="center">
    A modular monolith portfolio project designed to run locally on Ubuntu using k3s, Ansible provisioning, and a GitHub Actions → ArgoCD CI/CD workflow.
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project">About The Project</a></li>
    <li><a href="#getting-started">Project Plan</a></li>
    <li><a href="#purpose">Purpose</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>

## About The Project

**DevOps Portfolio Pipeline** will be a full-stack personal portfolio project implemented as a **modular monolith**, composed of a **Next.js frontend** and **Golang backend**, each deployed in their own Pod on a **k3s cluster running locally on Ubuntu (bare metal)**.

The cluster will be provisioned automatically using the official [**k3s-ansible**](https://github.com/k3s-io/k3s-ansible) playbook, with **GitHub Actions** building and pushing container images to **GitHub Container Registry (GHCR)**.  
**ArgoCD**, running inside k3s, will continuously sync new images from GHCR to the cluster using Helm charts.

### Planned Features
- **Architecture:** Modular monolith with separate Deployments for Next.js, Go API, and Postgres  
- **Networking:** Service-to-Service communication inside cluster; Traefik handles Ingress with custom hostname (e.g., `https://portfolio.local`)  
- **Database:** Postgres running as a StatefulSet with persistent local storage  
- **Authentication:** **NextAuth** with two user roles  
  - **Guest:** Public view of projects  
  - **Admin:** Authenticated CRUD access for project management  
- **CI/CD:**  
  - **GitHub Actions** → build + push images to GHCR  
  - **ArgoCD** → automatically sync Helm releases into k3s  
- **Provisioning:** Ansible playbook from [k3s-ansible](https://github.com/k3s-io/k3s-ansible) for bootstrapping the local cluster  
- **Monitoring:** Prometheus + Grafana stack for observability  
- **Security & Secrets:** Kubernetes Secrets for MVP; future integration with SOPS  
- **Deployment Strategy:** One Pod per container, single-node setup for local development

## Project Plan

This project will be built and deployed locally, using k3s as a lightweight Kubernetes distribution.  
All provisioning, configuration, and CI/CD automation will be gradually implemented as the app matures.

> **Planned structure**
```
/frontend        # Next.js (Node 20+) + NextAuth
/backend         # Go API (Gin or net/http) with REST endpoints
/deploy/helm     # Helm chart for all services (frontend, backend, postgres)
/infra/ansible   # Inventory and vars for k3s-ansible provisioning
```

### Prerequisites (Planned)
| Requirement | Description |
|--------------|-------------|
| OS | Ubuntu 22.04 LTS (bare metal) |
| Cluster | k3s provisioned via [k3s-ansible](https://github.com/k3s-io/k3s-ansible) |
| Registry | GitHub Container Registry (GHCR) |
| CI/CD Tools | GitHub Actions + ArgoCD |
| Utilities | `ansible`, `docker`, `helm`, `kubectl`, `argocd`, `git`, `python3` |
| Hostname | Custom domain (e.g., `portfolio.local`) served by Traefik |
| Database | PostgreSQL (StatefulSet, local PVC) |

## Purpose

This project will serve as a **personal DevOps learning environment** and **showcase portfolio**, simulating a production-style setup entirely on a local machine.  
The focus is to gain hands-on experience building, containerizing, and automating full-stack applications in a reproducible, infrastructure-as-code approach.

## Roadmap

### Phase 1 — Application Development
- [ ] Initialize frontend (Next.js) and backend (Go) projects  
- [ ] Implement REST API endpoints and connect to Postgres  
- [ ] Add authentication with NextAuth (Guest/Admin roles)  
- [ ] Test full CRUD functionality locally using Docker Compose  

### Phase 2 — Local Cluster Setup
- [ ] Provision local k3s cluster using **k3s-ansible**  
- [ ] Deploy PostgreSQL via StatefulSet  
- [ ] Create Deployments and Services for frontend and backend  
- [ ] Configure Traefik Ingress for custom hostname  

### Phase 3 — Helm & Configuration Management
- [ ] Create unified Helm chart (frontend, backend, database)  
- [ ] Externalize environment variables and secrets via Helm values  
- [ ] Test Helm install/upgrade flow on local k3s  

### Phase 4 — CI/CD Automation
- [ ] Configure GitHub Actions workflow to build + push to GHCR  
- [ ] Install ArgoCD in k3s and connect to repository  
- [ ] Automate ArgoCD syncs for Helm releases  
- [ ] Verify pipeline: Git push → GHCR update → ArgoCD sync → new deployment  

### Phase 5 — Observability & Finalization
- [ ] Install Prometheus + Grafana stack in k3s  
- [ ] Expose `/metrics` endpoint on backend  
- [ ] Create Grafana dashboards for request rate, latency, and errors  
- [ ] Write project documentation and lessons learned  

## Contact
**Shawn Nabizada**  
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555)](https://www.linkedin.com/in/shawn-nabizada/)  
[![Gmail](https://img.shields.io/badge/-Gmail-red?logo=gmail&logoColor=white&style=for-the-badge)](mailto:shawn.nabizada@gmail.com)
