<a id="readme-top"></a>

<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
<!--
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![project_license][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]
-->



<!-- PROJECT LOGO -->
<div align="center">
  <!--
  <a href="https://github.com/github_username/repo_name">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>
  -->

<h3 align="center">DevOps Portfolio Pipeline</h3>

  <p align="center">
    A production-style CI/CD pipeline project designed to automate builds, deployments, and observability for a Go + React portfolio app.
    <br />
    <a href="https://github.com/shawn-nabizada/devops-portfolio-pipeline"><strong>Explore the docs »</strong></a>
    <br />
    <!--
    <br />
    <a href="https://github.com/github_username/repo_name">View Demo</a>
    &middot;
    <a href="https://github.com/github_username/repo_name/issues/new?labels=bug&template=bug-report---.md">Report Bug</a>
    &middot;
    <a href="https://github.com/github_username/repo_name/issues/new?labels=enhancement&template=feature-request---.md">Request Feature</a>
    -->
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#key-features">Key Features</a></li>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#purpose">Purpose</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>




<!-- ABOUT THE PROJECT -->
## About The Project

**DevOps Portfolio Pipeline** is a personal DevOps project that demonstrates the full lifecycle of application delivery — from source code to deployment, monitoring, and security.  
It features a microservices-inspired setup with **Golang (API)** and **React (frontend)**, fully containerized and deployed to **AWS EKS** using automated pipelines and Infrastructure as Code.

This project simulates a real-world CI/CD environment for continuous learning and demonstration purposes.

### Key Features
- Automated build, test, and deploy pipelines with **Jenkins** and **GitHub Actions**
- Containerized **Golang API** and **React frontend** with **Docker**
- Infrastructure provisioning via **Terraform**
- Configuration management and deployment via **Ansible**
- Blue/Green deployments using **Helm**
- Integrated observability with **Prometheus** and **Grafana**
- Image scanning and security enforcement with **Trivy**

<p align="right">(<a href="#readme-top">back to top</a>)</p>



### Built With

[![Go][Go-badge]][Go-url]  
[![React][React-badge]][React-url]  
[![Docker][Docker-badge]][Docker-url]  
[![Kubernetes][Kubernetes-badge]][Kubernetes-url]  
[![Terraform][Terraform-badge]][Terraform-url]  
[![Ansible][Ansible-badge]][Ansible-url]  
[![AWS][AWS-badge]][AWS-url]  
[![Prometheus][Prometheus-badge]][Prometheus-url]  
[![Grafana][Grafana-badge]][Grafana-url]  
[![Jenkins][Jenkins-badge]][Jenkins-url]  
[![Trivy][Trivy-badge]][Trivy-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

Work in progress.

### Prerequisites


### Installation


<p align="right">(<a href="#readme-top">back to top</a>)</p>



## Purpose

This project was created as a personal learning initiative to **understand and apply the fundamentals of DevOps engineering** in a practical, end-to-end environment.  
The goal is to simulate the real-world workflow of a modern DevOps pipeline — from development and automation to deployment and monitoring.

### Learning Objectives
- **Understand CI/CD principles:** Build a continuous integration and delivery pipeline with Jenkins to automate code testing, building, and deployment.
- **Containerization & orchestration:** Learn how to package applications using Docker and deploy them on Kubernetes (EKS).
- **Infrastructure as Code (IaC):** Use Terraform to provision AWS resources and Ansible to automate environment configuration.
- **Observability:** Gain experience setting up Prometheus and Grafana for metrics, alerts, and dashboards.
- **Security in pipelines:** Integrate image scanning with Trivy to identify vulnerabilities early in the CI/CD process.
- **Deployment strategies:** Explore blue/green deployments and safe rollout techniques using Helm and Ansible.
- **Collaboration & documentation:** Practice Git branching, pull requests, and structured documentation to maintain production-quality standards.

### Outcome
By the end of this project, I aim to:
- Strengthen my understanding of DevOps pipelines and cloud-native architecture.
- Build a reusable reference for future automation projects.
- Develop the skills required to deploy reliable, secure, and observable applications at scale.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ROADMAP -->
## Roadmap
Work in progress.

### Phase 1 — Core CI/CD Pipeline (MVP)
- [ ] Containerize the Golang API and React frontend using Docker
- [ ] Build a Jenkins pipeline to automate build, test, scan (Trivy), and deploy stages
- [ ] Push Docker images to AWS ECR
- [ ] Provision AWS EKS cluster using Terraform
- [ ] Deploy workloads with Helm and verify environment stability

### Phase 2 — Infrastructure & Configuration Automation
- [ ] Automate configuration management and deployments using Ansible
- [ ] Introduce environment separation (dev, staging, prod) via Helm values
- [ ] Implement Blue/Green and Rolling Deployments for safe updates
- [ ] Define IaC best practices: remote Terraform state, variable modules, and workspaces

### Phase 3 — Observability & Security
- [ ] Integrate Prometheus and Grafana for monitoring cluster, pods, and app metrics
- [ ] Add alerting and health dashboards for uptime tracking
- [ ] Automate image scanning with Trivy and integrate reports into Jenkins
- [ ] Introduce log aggregation (ELK or Loki) for centralized observability
- [ ] Enforce least-privilege IAM roles and secrets management via AWS Secrets Manager

### Phase 4 — Microservices & Scalability
- [ ] Split the monolithic app into multiple microservices (profile-svc, projects-svc, metrics-svc)
- [ ] Implement service discovery and API versioning
- [ ] Use NGINX Ingress for unified routing and TLS termination
- [ ] Add message-based communication with AWS SQS or NATS

### Phase 5 — GitOps & Continuous Improvement
- [ ] Migrate CI/CD to a GitOps model using ArgoCD
- [ ] Introduce automated testing pipelines (unit + integration)
- [ ] Add cost monitoring and autoscaling policies
- [ ] Document best practices and publish full pipeline guide

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- CONTACT -->
## Contact
**Shawn Nabizada**
<br />
[![LinkedIn][linkedin-shield]][linkedin-url]
[![Gmail][gmail-shield]][gmail-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>




<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/github_username/repo_name.svg?style=for-the-badge
[contributors-url]: https://github.com/github_username/repo_name/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/github_username/repo_name.svg?style=for-the-badge
[forks-url]: https://github.com/github_username/repo_name/network/members
[stars-shield]: https://img.shields.io/github/stars/github_username/repo_name.svg?style=for-the-badge
[stars-url]: https://github.com/github_username/repo_name/stargazers
[issues-shield]: https://img.shields.io/github/issues/github_username/repo_name.svg?style=for-the-badge
[issues-url]: https://github.com/github_username/repo_name/issues
[license-shield]: https://img.shields.io/github/license/github_username/repo_name.svg?style=for-the-badge
[license-url]: https://github.com/github_username/repo_name/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/shawn-nabizada/
[gmail-shield]: https://img.shields.io/badge/-Gmail-red?logo=gmail&logoColor=white&style=for-the-badge  
[gmail-url]: mailto:shawn.nabizada@gmail.com
[product-screenshot]: images/screenshot.png
<!-- Shields.io badges. You can a comprehensive list with many more badges at: https://github.com/inttter/md-badges -->
[Go-badge]: https://img.shields.io/badge/Go-00ADD8?logo=go&logoColor=white&style=for-the-badge  
[Go-url]: https://golang.org/  
[React-badge]: https://img.shields.io/badge/React-20232A?logo=react&logoColor=61DAFB&style=for-the-badge  
[React-url]: https://reactjs.org/  
[Docker-badge]: https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white&style=for-the-badge  
[Docker-url]: https://www.docker.com/  
[Kubernetes-badge]: https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white&style=for-the-badge  
[Kubernetes-url]: https://kubernetes.io/  
[Terraform-badge]: https://img.shields.io/badge/Terraform-623CE4?logo=terraform&logoColor=white&style=for-the-badge  
[Terraform-url]: https://www.terraform.io/  
[Ansible-badge]: https://img.shields.io/badge/Ansible-EE0000?logo=ansible&logoColor=white&style=for-the-badge  
[Ansible-url]: https://www.ansible.com/  
[AWS-badge]: https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=white&style=for-the-badge  
[AWS-url]: https://aws.amazon.com/  
[Prometheus-badge]: https://img.shields.io/badge/Prometheus-E6522C?logo=prometheus&logoColor=white&style=for-the-badge  
[Prometheus-url]: https://prometheus.io/  
[Grafana-badge]: https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white&style=for-the-badge  
[Grafana-url]: https://grafana.com/  
[Jenkins-badge]: https://img.shields.io/badge/Jenkins-D24939?logo=jenkins&logoColor=white&style=for-the-badge  
[Jenkins-url]: https://www.jenkins.io/  
[Trivy-badge]: https://img.shields.io/badge/Trivy-1903FC?logo=aqua&logoColor=white&style=for-the-badge  
[Trivy-url]: https://aquasecurity.github.io/trivy/  
