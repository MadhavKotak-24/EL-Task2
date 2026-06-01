# Jenkins CI/CD Pipeline for Node.js Application

## Project Overview

This project demonstrates the implementation of a Continuous Integration and Continuous Deployment (CI/CD) pipeline using Jenkins. The pipeline automates the process of fetching source code from GitHub, building the application, executing tests, and deploying the application through a Jenkins Pipeline.

The primary objective of this project is to understand how Jenkins can be used to automate software delivery workflows and reduce manual intervention during application deployment.

---

# Objectives

* Install and configure Jenkins.
* Connect Jenkins with a GitHub repository.
* Create a Jenkins Pipeline using a Jenkinsfile.
* Automate build, test, and deployment stages.
* Trigger pipeline execution through Jenkins.
* Understand CI/CD concepts and Jenkins Pipeline architecture.

---

# Technologies Used

| Technology       | Purpose                 |
| ---------------- | ----------------------- |
| Jenkins          | CI/CD Automation Server |
| GitHub           | Source Code Repository  |
| Git              | Version Control         |
| Docker           | Containerization        |
| Node.js          | Sample Application      |
| Jenkins Pipeline | Pipeline as Code        |

---

# Project Architecture

```text
Developer
    │
    ▼
GitHub Repository
    │
    ▼
Jenkins Pipeline
    │
    ├── Checkout Source Code
    │
    ├── Build Application
    │
    ├── Run Tests
    │
    └── Deploy Application
```

---

# CI/CD Workflow

```text
Code Commit
     │
     ▼
GitHub Repository
     │
     ▼
Jenkins Pipeline Trigger
     │
     ▼
Checkout Stage
     │
     ▼
Build Stage
     │
     ▼
Test Stage
     │
     ▼
Deploy Stage
     │
     ▼
Pipeline Success
```

---

# Project Structure

```text
EL-Task2/
│
├── app.js
├── package.json
├── Dockerfile
├── Jenkinsfile
├── .gitignore
└── README.md
```

---

# Jenkins Setup Process

## Step 1: Install Jenkins Using Docker

Pull Jenkins image:

```bash
docker pull jenkins/jenkins:lts
```

Create Jenkins container:

```bash
docker run -d --name jenkins -p 9090:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts
```

---

## Step 2: Access Jenkins

Open Jenkins Dashboard:

```text
http://localhost:9090
```

Unlock Jenkins using the initial administrator password.

Install the suggested plugins and create the administrator account.

---

## Step 3: Create GitHub Repository

Create a new GitHub repository and upload:

* Node.js Application
* Dockerfile
* Jenkinsfile
* README.md

---

## Step 4: Create Jenkins Pipeline

A Jenkins Pipeline Job was created using:

```text
Pipeline Script from SCM
```

Repository Source:

```text
GitHub Repository
```

Branch:

```text
main
```

Script Path:

```text
Jenkinsfile
```

---

# Jenkinsfile Explanation

The pipeline consists of four stages:

## Checkout Stage

Retrieves the latest source code from GitHub.

```text
Checkout Source Code
```

---

## Build Stage

Builds the application.

```text
Build Application
```

---

## Test Stage

Runs automated tests.

```text
Run Tests
```

---

## Deploy Stage

Deploys the application.

```text
Deploy Application
```

---

# Pipeline Stages

```text
Stage 1 : Checkout
Stage 2 : Build
Stage 3 : Test
Stage 4 : Deploy
```

---

# Pipeline Execution

Whenever the Jenkins job is executed:

1. Jenkins connects to GitHub.
2. Source code is downloaded.
3. Build stage executes.
4. Test stage executes.
5. Deploy stage executes.
6. Pipeline reports SUCCESS.

---

# Challenges Faced

During implementation, several issues were encountered and resolved:

### Git Branch Error

Issue:

```text
refs/heads/master not found
```

Solution:

```text
Changed Jenkins branch configuration from master to main.
```

---

### Node.js Not Found

Issue:

```text
npm: not found
```

Solution:

```text
Updated Jenkins execution strategy and pipeline configuration.
```

---

### Docker Not Found

Issue:

```text
docker: not found
```

Solution:

```text
Configured Jenkins environment to support Docker commands.
```

---

### Docker Permission Issues

Issue:

```text
permission denied while trying to connect to Docker daemon
```

Solution:

```text
Adjusted Jenkins configuration and simplified pipeline execution.
```

---

# Learning Outcomes

Through this project, the following concepts were learned:

* Continuous Integration (CI)
* Continuous Deployment (CD)
* Jenkins Installation and Configuration
* Jenkins Pipelines
* Pipeline as Code
* GitHub Integration
* Build Automation
* Automated Testing
* Deployment Automation
* Troubleshooting Jenkins Pipelines

---

# Future Improvements

Potential enhancements include:

* GitHub Webhook Integration
* Docker Image Build and Push
* DockerHub Integration
* AWS EC2 Deployment
* Kubernetes Deployment
* Email Notifications
* Slack Notifications
* Automated Rollback Mechanism

---

# Conclusion

This project successfully demonstrates a Jenkins-based CI/CD pipeline for a Node.js application. The pipeline automates the software delivery workflow by performing source code checkout, build, test, and deployment operations through Jenkins, thereby reducing manual effort and improving development efficiency.
