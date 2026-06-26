\# 🚀 GitOps Continuous Delivery on Kubernetes using ArgoCD



> A production-style GitOps Continuous Delivery project demonstrating automated Kubernetes deployments using ArgoCD, Docker, DockerHub, GitHub, and Minikube.



!\[GitHub](https://img.shields.io/badge/GitHub-Repository-black?logo=github)

!\[Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker\\\&logoColor=white)

!\[Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes\\\&logoColor=white)

!\[ArgoCD](https://img.shields.io/badge/ArgoCD-EF7B4D?logo=argo\\\&logoColor=white)

!\[License](https://img.shields.io/badge/License-MIT-green)



\---



\# 📖 Project Overview



This project demonstrates a \*\*GitOps-based Continuous Delivery pipeline\*\* using \*\*ArgoCD\*\* on a Kubernetes cluster.



The application is containerized using Docker, pushed to DockerHub, and deployed on Kubernetes through ArgoCD. Instead of manually applying Kubernetes manifests, GitHub acts as the \*\*Single Source of Truth\*\*, and ArgoCD continuously monitors the repository to synchronize the Kubernetes cluster automatically.



The project also demonstrates rolling updates by deploying multiple versions of the application (\*\*v1 → v2\*\*) using Git commits.



\---



\# ✨ Features



\* 🚀 GitOps Continuous Delivery

\* ☸️ Kubernetes Deployment

\* 📦 Docker Containerization

\* 🐳 DockerHub Image Repository

\* 🔄 Automatic Synchronization using ArgoCD

\* 📁 GitHub as Single Source of Truth

\* 🔁 Rolling Updates

\* 🌐 Nginx Web Server

\* ⚡ Version-based Deployment (v1 \& v2)



\---



\# 🛠️ Tech Stack



| Technology            | Purpose                    |

| --------------------- | -------------------------- |

| Docker                | Containerization           |

| DockerHub             | Image Registry             |

| Kubernetes (Minikube) | Container Orchestration    |

| ArgoCD                | GitOps Continuous Delivery |

| Git                   | Version Control            |

| GitHub                | Source Repository          |

| HTML                  | Static Website             |

| Nginx                 | Web Server                 |



\---



\# 📂 Project Structure



```text

gitops-argocd-project/

│

├── app/

│   ├── Dockerfile

│   └── index.html

│

├── k8s/

│   ├── deployment.yaml

│   └── service.yaml

│

├── screenshots/

│

├── .gitignore

├── LICENSE

└── README.md

```



\---



\# 🏗️ Architecture



```text

&#x20;                   Developer

&#x20;                       │

&#x20;                       ▼

&#x20;              Modify Application Code

&#x20;                       │

&#x20;                       ▼

&#x20;                 Build Docker Image

&#x20;                       │

&#x20;                       ▼

&#x20;            Push Image to DockerHub

&#x20;                       │

&#x20;                       ▼

&#x20;        Update deployment.yaml Image Tag

&#x20;                       │

&#x20;                       ▼

&#x20;              Commit \& Push to GitHub

&#x20;                       │

&#x20;                       ▼

&#x20;         GitHub (Single Source of Truth)

&#x20;                       │

&#x20;                       ▼

&#x20;        ArgoCD Monitors Git Repository

&#x20;                       │

&#x20;                       ▼

&#x20;       Detects Changes Automatically

&#x20;                       │

&#x20;                       ▼

&#x20;     Synchronizes Kubernetes Cluster

&#x20;                       │

&#x20;                       ▼

&#x20;       Rolling Update of Application

&#x20;                       │

&#x20;                       ▼

&#x20;            Users Access New Version

```



\---



\# ⚙️ Prerequisites



Before running this project, install:



\* Docker Desktop

\* Kubernetes (Minikube)

\* kubectl

\* Git

\* ArgoCD CLI (Optional)

\* GitHub Account

\* DockerHub Account



\---



\# 🚀 Deployment Steps



\### 1️⃣ Clone Repository



```bash

git clone https://github.com/Puneet-Xt/gitops-argocd-project

cd gitops-argocd-project

```



\---



\### 2️⃣ Build Docker Image



```bash

docker build -t puneet8580/gitops-app:v1 ./app

```



\---



\### 3️⃣ Push Image to DockerHub



```bash

docker push puneet8580/gitops-app:v1

```



\---



\### 4️⃣ Deploy ArgoCD



```bash

kubectl create namespace argocd



kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

```



\---



\### 5️⃣ Expose ArgoCD Server



```bash

kubectl port-forward svc/argocd-server -n argocd 8080:443

```



Open:



```

https://localhost:8080

```



\---



\### 6️⃣ Create ArgoCD Application



\* Repository URL

\* Path → k8s

\* Destination → default namespace

\* Sync Application



\---



\# 🔄 GitOps Workflow



```text

Developer

&#x20;   │

&#x20;   ▼

Update Application

&#x20;   │

&#x20;   ▼

Docker Build

&#x20;   │

&#x20;   ▼

Push Docker Image

&#x20;   │

&#x20;   ▼

Update deployment.yaml

&#x20;   │

&#x20;   ▼

Git Commit

&#x20;   │

&#x20;   ▼

Git Push

&#x20;   │

&#x20;   ▼

GitHub Repository

&#x20;   │

&#x20;   ▼

ArgoCD Detects Changes

&#x20;   │

&#x20;   ▼

Automatic Synchronization

&#x20;   │

&#x20;   ▼

Kubernetes Rolling Update

&#x20;   │

&#x20;   ▼

Updated Application

```



\---



\# 📷 Screenshots



Add screenshots inside the \*\*screenshots\*\* folder.



\* 📌 Project Architecture

\* 📌 ArgoCD Dashboard

\* 📌 DockerHub Repository

\* 📌 GitHub Repository

\* 📌 Application Version 1

\* 📌 Application Version 2

\* 📌 kubectl get pods

\* 📌 Successful Sync Status



\---



\# 📈 Project Highlights



\* Implemented GitOps Continuous Delivery using ArgoCD.

\* Used GitHub as the Single Source of Truth.

\* Automated Kubernetes deployments.

\* Managed Docker image versioning.

\* Demonstrated zero-downtime rolling updates.

\* Eliminated manual deployment using GitOps practices.



\---



\# 🧠 Challenges Faced



\* Fixed Namespace configuration issues.

\* Resolved ImagePullBackOff errors.

\* Corrected Dockerfile naming issues.

\* Configured DockerHub image versioning.

\* Troubleshot ArgoCD synchronization problems.

\* Implemented successful rolling updates.



\---



\# 🎯 Learning Outcomes



After completing this project, I gained practical experience with:



\* GitOps Principles

\* Kubernetes Deployments

\* Docker Image Management

\* ArgoCD Synchronization

\* Rolling Updates

\* DockerHub Integration

\* Kubernetes Services

\* Production-style Continuous Delivery Workflow



\---



\# 👨‍💻 Author



\*\*Punnet Choudhary\*\*



Cloud \& DevOps Engineer



GitHub: https://github.com/Puneet-Xt



\---



\# ⭐ Support



If you found this project helpful, consider giving it a ⭐ on GitHub.



