# Mini Docker CI/CD Web App — Automated Container Build & Delivery

## Overview

This is my beginner-friendly DevOps mini project that combines a simple web application with Docker, Git, GitHub, Docker Hub, and GitHub Actions.

The project demonstrates how a web application can be packaged into a Docker image and automatically built and pushed to Docker Hub whenever changes are pushed to GitHub.

It was created as a practical project after working through Linux, Python, Docker, and Git hands on labs, with the goal of understanding how CI/CD works in a real DevOps workflow.

## Files Included

* index.html — Main web application page
* style.css — Styling for the web application
* Dockerfile — Instructions for building the Docker image
* .github/workflows/ci-cd.yml — GitHub Actions CI/CD workflow
* README.md — Project documentation
* Screenshots — Practical evidence of the Docker, Git, GitHub, and CI/CD work

## Project Workflow

Developer makes changes → Git → GitHub → GitHub Actions → Build Docker Image → Push to Docker Hub → Docker image can be pulled and run anywhere.

### CI — Continuous Integration

GitHub Actions automatically:

* Checks out the latest code
* Logs in to Docker Hub
* Builds the Docker image
* Verifies that the Docker build process works

### CD — Continuous Delivery

After the image is successfully built, GitHub Actions pushes the updated Docker image to Docker Hub.

This project demonstrates **Continuous Delivery of the Docker image**. It does not yet automatically deploy the application to a production server.


## Commands Used

### Linux & Project Setup

* ls
* clear
* cd ..
* cd Mini-Docker-CI-CD-Project
* nano index.html
* nano style.css
* python3 -m http.server 8000

### Docker Image Building

* nano Dockerfile
* docker build -t myproj .
* docker images
* docker build -t myproj .
* docker run -d -p 8080:80 --name devops-proj myproj
* docker ps
* docker ps -a

### Docker Container Management

* docker run -d -p 8080:80 --name test-web-app abdul623/my-web-app:latest
* docker stop 4f1491b17e65
* docker rm -f test-web-app
* docker rm -f $(docker ps -aq)
* docker ps -a

### Docker Images Management

* docker images
* docker rm -f nonroot-user:latest
* docker rm -f 48f97fe3e604 8541484afbc9 4bc6bc963e6d
* docker rmi -f 48f97fe3e604 8541484afbc9 4bc6bc963e6d
* docker rmi -f $(docker images -aq)
* docker images

### Docker Hub

* docker login -u abdul623
* docker pull abdul623/my-web-app:latest
* docker run -d -p 8080:80 --name test-web-app abdul623/my-web-app:latest
* docker ps
* docker ps -a

### Git & GitHub

* git init
* git status
* git add .
* git commit -m "build Docker CI CD project"
* git push origin main
* git clone [GitHub repository]
* git log -1 --oneline
* git pull --rebase origin main
* git push origin main

### GitHub Actions

* mkdir -p .github/workflows
* nano .github/workflows/ci-cd.yml
* git add .github/workflows/ci-cd.yml
* git commit -m "Add Docker CI pipeline"
* git push origin main

## GitHub Actions Workflow

The CI/CD workflow uses GitHub Actions to automate the Docker process.

The workflow:

1. Checks out the repository.
2. Logs in to Docker Hub using GitHub Secrets.
3. Builds the Docker image.
4. Tags the image with the Docker Hub repository name.
5. Pushes the image to Docker Hub.
6. Makes the latest image available for deployment or manual testing.

Docker Hub credentials are stored securely as GitHub Secrets rather than being written directly into the workflow.

## Output

The final result is a working containerized web application.

The application can be:

* Built as a Docker image
* Run as a Docker container
* Tested locally through port 8080
* Stored on Docker Hub
* Automatically rebuilt through GitHub Actions
* Automatically pushed to Docker Hub after changes are committed and pushed to GitHub

## What I Learned

This project was my first practical mini project combining several technologies I had previously learned separately.

After working through Linux, Python, Docker, and Git labs, I brought those skills together into one practical DevOps workflow. It involved a lot of testing, mistakes, troubleshooting, rebuilding containers, managing images, fixing authentication issues, and updating the GitHub Actions workflow.

Through this project, I learned how Docker packages an application into a portable container, how Git tracks project changes, how GitHub stores the source code, how Docker Hub stores container images, and how GitHub Actions can automate the build and delivery process.

Most importantly, I learned the practical idea behind CI/CD: **when developers push new code, automation can take that code, build it, package it, and deliver the updated application artifact without manually repeating every step.**

## Key Concepts

* Linux command line
* Git & GitHub
* Docker
* Docker Images
* Docker Containers
* Dockerfile
* Docker Hub
* GitHub Actions
* Continuous Integration
* Continuous Delivery
* CI/CD automation
* Containerized web applications
* GitHub Secrets
* Basic DevOps workflow

## The Whole Lab in One Picture

**HTML + CSS**

↓

**Dockerfile**

↓

**Docker Image**

↓

**Docker Container**

↓

**Git**

↓

**GitHub**

↓

**GitHub Actions**

↓

**Docker Image Build**

↓

**Docker Hub**

↓

**Ready for Deployment**

## Final Result

this simple web application was successfully containerized with Docker and connected to a GitHub Actions workflow that automatically builds and pushes the Docker image to Docker Hub.

This mini project gave me practical experience with the foundation of a real-world DevOps CI/CD pipeline and provided a strong starting point for moving toward more advanced projects involving cloud deployment, infrastructure as code, security, and automated production deployments.

