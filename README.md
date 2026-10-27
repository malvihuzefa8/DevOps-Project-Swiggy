# 🍔 Swiggy Clone App

A full-stack food delivery web application inspired by Swiggy. This project is built with **Node.js** and **React**, containerized with **Docker**, and deployed on **AWS EC2** using a complete **Jenkins CI/CD pipeline** with integrated security scanning.

## 📱 About the App

The Swiggy Clone allows users to:
- Browse restaurants and food items
- Add items to cart
- Place orders
- View order history

The application is designed to demonstrate a real-world DevOps workflow — from code commit to production deployment — with automated security checks at every stage.

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React.js |
| Backend | Node.js, Express |
| Containerization | Docker |
| CI/CD | Jenkins |
| Security | Trivy, SonarQube, OWASP Dependency-Check |
| Cloud | AWS EC2 |
| IaC | Terraform |

## 🚀 CI/CD Pipeline

The Jenkins pipeline automates the following stages:

1. Clean workspace
2. Checkout code from GitHub
3. Install dependencies (`npm ci`)
4. OWASP Dependency-Check (dependency vulnerabilities)
5. SonarQube analysis (code quality & security)
6. Trivy FS scan (filesystem vulnerabilities & secrets)
7. Docker build & push to Docker Hub
8. Trivy image scan (container vulnerabilities)
9. Deploy to EC2 as a Docker container


# Build the Docker image
docker build -t huzefa2612/swiggy:latest .

# Run the container
docker run -d --name swiggy -p 3000:3000 huzefa2612/swiggy:latest