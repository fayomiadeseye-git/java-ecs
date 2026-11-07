# CloudBridge Technologies - Java Web Application

This repository contains a modern **Spring Boot 3 (Java 17)** web application, styled with an **elegant deep navy and warm gold container aesthetic**, complete with a production-ready **Dockerfile** for pushing to **Amazon ECR**.

---

## 🛠️ Tech Stack
- **Backend:** Java 17, Spring Boot 3.2.3, Thymeleaf Engine
- **Frontend:** HTML5, CSS3 (Custom Dark Gold Palette), JavaScript
- **Containerization:** Docker, Multi-Stage Build
- **Target Registry:** AWS Elastic Container Registry (ECR)

---

## 🚀 How to Run Locally with Maven

```bash
# Navigate into project directory
cd cloudbridge-app

# Build and run with Maven Wrapper or Maven
mvn clean spring-boot:run
```

Access the application in your browser at: `http://localhost:8080`

---

## 📦 How to Build Docker Image & Push to AWS ECR

### Step 1: Build Docker Image
```bash
docker build -t cloudbridge-website .
```

### Step 2: Authenticate Docker to AWS ECR
```bash
aws ecr get-login-password --region <your-region> | docker login --username AWS --password-stdin <your-account-id>.dkr.ecr.<your-region>.amazonaws.com
```

### Step 3: Create ECR Repository (If not existing)
```bash
aws ecr create-repository --repository-name cloudbridge-website --region <your-region>
```

### Step 4: Tag & Push Image to ECR
```bash
docker tag cloudbridge-website:latest <your-account-id>.dkr.ecr.<your-region>.amazonaws.com/cloudbridge-website:latest

docker push <your-account-id>.dkr.ecr.<your-region>.amazonaws.com/cloudbridge-website:latest
```

---

## 🐙 Push to GitHub / Git Repository

```bash
git init
git add .
git commit -m "Initial commit: Restyled Java Spring Boot application with Dockerfile"
git branch -M main
git remote add origin git@github.com:<your-username>/cloudbridge-website.git
git push -u origin main
```
