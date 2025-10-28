<a id="readme-top"></a>

<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->



<!-- PROJECT LOGO -->
<div align="center">

<h3 align="center">DevOps Portfolio Pipeline</h3>

  <p align="center">
    A planned modular-monolith portfolio app that will combine a Next.js frontend and Go backend, containerized and deployed to AWS EKS through a CI/CD pipeline.
    <br />
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#key-features">Planned Features</a></li>
        <li><a href="#built-with">Tech Stack</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Project Plan</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites (Planned)</a></li>
        <li><a href="#installation">Setup & Installation (Draft)</a></li>
      </ul>
    </li>
    <li><a href="#purpose">Purpose</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>




<!-- ABOUT THE PROJECT -->
## About The Project

**DevOps Portfolio Pipeline** will be a full-stack personal portfolio system implemented as a **modular monolith**, featuring a **Next.js frontend** and **Golang backend** running as two containers inside a single Kubernetes Pod. The project will initially be tested using **k3s**, a lightweight Kubernetes distribution, before transitioning to **AWS EKS** for production deployment.
It will use **AWS RDS PostgreSQL** for data persistence, with CI/CD automation handled by **GitHub Actions** and **ArgoCD** for deployment to **AWS EKS**.  
Observability will be achieved with **Prometheus** and **Grafana**, and authentication will be managed through **NextAuth**.

This project is being developed as a hands-on demonstration of modern DevOps workflows and cloud-native software design.

### Planned Features
- **Architecture:** Modular monolith with **Next.js (frontend)** and **Go API (backend)** in one Pod
- **Networking:** Internal-only API (`127.0.0.1:<api-port>`) for secure in-Pod communication
- **Database:** **AWS RDS PostgreSQL**
- **Authentication:** **NextAuth** with two user roles  
  - **Guest:** Public access to view portfolio content  
  - **Admin:** Authenticated access to create, update, or delete projects
- **CI/CD Pipeline:**  
  - **GitHub Actions** for build and push to ECR  
  - **ArgoCD** for automated deployment to EKS
- **Monitoring:** **Prometheus** metrics endpoint on Go backend and **Grafana** dashboards
- **Secrets & Config:** Stored securely in Kubernetes or AWS Secrets Manager
- **Infrastructure as Code:** Single Helm chart deployment for repeatability

<p align="right">(<a href="#readme-top">back to top</a>)</p>



### Tech Stack

[![Go][Go-badge]][Go-url]  
[![Next.js][React-badge]][React-url]  
[![Docker][Docker-badge]][Docker-url]  
[![Kubernetes][Kubernetes-badge]][Kubernetes-url]  
[![AWS][AWS-badge]][AWS-url]  
[![Postgres][Postgres-badge]][Postgres-url]  
[![GitHub Actions][Actions-badge]][Actions-url]  
[![ArgoCD][ArgoCD-badge]][ArgoCD-url]  
[![Prometheus][Prometheus-badge]][Prometheus-url]  
[![Grafana][Grafana-badge]][Grafana-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Project Plan

This section outlines how the project will eventually be structured and deployed.  
The commands and setup below are **draft steps** — implementation will happen in future milestones.

> **Intended repo structure**
```
/frontend        # Next.js (Node 20+) with NextAuth
/backend         # Go API (net/http or Gin), /healthz and /metrics
/deploy/helm     # Helm chart: one Deployment, two containers, one Service (frontend)
```

### Prerequisites (Planned)
- AWS Account with EKS, ECR, RDS, ACM, and IAM permissions  
- Tools to be used: `kubectl`, `helm`, `k3s`, `awscli`, and `argocd` 
- ALB Ingress Controller and ArgoCD will be installed on EKS  
- PostgreSQL database (AWS RDS) for persistent data storage

**Expected Configuration**
| Item | Default | Notes |
|------|----------|-------|
| Region | `ca-central-1` | Planned AWS region |
| Ports | Backend `8080`, Frontend `3000` | |
| DB Name | `portfolio_db` | Will be created on RDS |
| Roles | Guest (view), Admin (CRUD) | |
| API Access | Private (in-Pod only) | Frontend communicates internally |

---

### Setup & Installation (Draft)

This section will eventually include detailed setup commands for deploying the application.  
For now, it serves as a **blueprint** for future automation.

1. **Create ECR Repositories (Planned)**  
   The app will use two ECR repos: `frontend` and `backend`.

2. **Configure GitHub OIDC Role (Planned)**  
   GitHub Actions will assume an AWS IAM role for ECR access.

3. **Provision AWS RDS Postgres (Planned)**  
   The RDS instance will store portfolio and user data.

4. **Define Secrets (Future)**  
   Application secrets will be managed via Kubernetes or AWS Secrets Manager.

5. **Set Up CI/CD (Future)**  
   GitHub Actions → ECR → ArgoCD → EKS workflow will be automated through YAML pipelines.

6. **Observability Stack (Planned)**  
   Prometheus and Grafana will be installed for monitoring and alerting.

7. **Testing & Verification (Future)**  
   Health checks and readiness probes will ensure a stable deployment before production rollout.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



## Purpose

This project is being developed as a **DevOps learning initiative** to explore the full lifecycle of cloud-native application delivery.  
The intent is to gain hands-on experience with CI/CD automation, infrastructure orchestration, and modern software deployment workflows.

### Learning Goals
- Understand how to automate build, test, and deployment pipelines  
- Practice containerization and orchestration using Docker and Kubernetes  
- Learn Infrastructure-as-Code principles using Helm and declarative YAML manifests  
- Integrate monitoring and observability with Prometheus and Grafana  
- Implement secure authentication flows with NextAuth  
- Strengthen AWS DevOps fundamentals with EKS, RDS, ECR, and IAM

### Expected Outcomes
- A fully functional cloud-deployed portfolio application  
- A reusable template for future DevOps projects  
- A documented, production-like reference for end-to-end delivery

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ROADMAP -->
## Roadmap

### Phase 1 — Frontend Development
- [ ] Initialize the Next.js project structure  
- [ ] Design core pages (Home, Projects, Contact)  
- [ ] Implement responsive layout and reusable UI components  
- [ ] Set up client-side routing and data fetching structure  
- [ ] Integrate **NextAuth** for authentication (guest/admin roles)  
- [ ] Build admin-only CRUD interface for managing projects  

### Phase 2 — Backend Development
- [ ] Initialize Go API with basic routing (Gin or net/http)  
- [ ] Implement `/healthz` and `/metrics` endpoints  
- [ ] Connect backend to **PostgreSQL** (local instance or RDS later)  
- [ ] Define and apply schema migrations (projects table)  
- [ ] Expose REST endpoints for CRUD operations on projects  
- [ ] Add authentication middleware to protect admin routes  
- [ ] Test local end-to-end flow (frontend ↔ backend ↔ database)  

### Phase 3 — Integration & Testing
- [ ] Integrate frontend with backend API (private internal calls)  
- [ ] Validate full CRUD functionality from the admin UI  
- [ ] Add form validation, error handling, and loading states  
- [ ] Conduct local testing using **k3s** (lightweight Kubernetes distribution)  
- [ ] Finalize environment variable configuration and secrets layout  

### Phase 4 — DevOps Setup
- [ ] Containerize both applications with Docker  
- [ ] Create a single Helm chart for the modular monolith (frontend + backend Pod)  
- [ ] Configure environment variables and secrets through Helm values  
- [ ] Prepare GitHub Actions workflows for build and push to ECR  
- [ ] Deploy to **k3s** for initial CI/CD pipeline validation  

### Phase 5 — CI/CD & Observability Rollout
- [ ] Transition deployment from k3s to **AWS EKS**  
- [ ] Automate CI/CD pipeline with **GitHub Actions → ECR → ArgoCD → EKS**  
- [ ] Configure **ArgoCD** for automated deployments  
- [ ] Add liveness and readiness probes to both containers  
- [ ] Install **Prometheus** and **Grafana** for monitoring  
- [ ] Integrate metrics dashboards and confirm `/metrics` scraping  
- [ ] Document final deployment and operational procedures  

<p align="right">(<a href="#readme-top">back to top</a>)</p>




<!-- CONTACT -->
## Contact
**Shawn Nabizada**  
[![LinkedIn][linkedin-shield]][linkedin-url]  
[![Gmail][gmail-shield]][gmail-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>




<!-- MARKDOWN LINKS & IMAGES -->
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/shawn-nabizada/
[gmail-shield]: https://img.shields.io/badge/-Gmail-red?logo=gmail&logoColor=white&style=for-the-badge  
[gmail-url]: mailto:shawn.nabizada@gmail.com
[Go-badge]: https://img.shields.io/badge/Go-00ADD8?logo=go&logoColor=white&style=for-the-badge  
[Go-url]: https://golang.org/  
[React-badge]: https://img.shields.io/badge/Next.js-000000?logo=nextdotjs&logoColor=white&style=for-the-badge  
[React-url]: https://nextjs.org/  
[Docker-badge]: https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white&style=for-the-badge  
[Docker-url]: https://www.docker.com/  
[Kubernetes-badge]: https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white&style=for-the-badge  
[Kubernetes-url]: https://kubernetes.io/  
[AWS-badge]: https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=white&style=for-the-badge  
[AWS-url]: https://aws.amazon.com/  
[Postgres-badge]: https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white&style=for-the-badge
[Postgres-url]: https://www.postgresql.org/
[Actions-badge]: https://img.shields.io/badge/GitHub%20Actions-2088FF?logo=githubactions&logoColor=white&style=for-the-badge
[Actions-url]: https://docs.github.com/actions
[ArgoCD-badge]: https://img.shields.io/badge/ArgoCD-FE6D00?logo=argo&logoColor=white&style=for-the-badge
[ArgoCD-url]: https://argo-cd.readthedocs.io/
[Prometheus-badge]: https://img.shields.io/badge/Prometheus-E6522C?logo=prometheus&logoColor=white&style=for-the-badge  
[Prometheus-url]: https://prometheus.io/  
[Grafana-badge]: https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white&style=for-the-badge  
[Grafana-url]: https://grafana.com/  
