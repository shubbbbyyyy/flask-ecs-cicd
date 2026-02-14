# flask-ecs-cicd
Automated deployment of a Flask web application on AWS ECS Fargate using Terraform and GitHub Actions. Implements a secure 2-tier architecture with VPC, public subnet, and proper IAM roles, demonstrating a full CI/CD pipeline

# flask-ecs-cicd

[![Terraform](https://img.shields.io/badge/Terraform-Cloud-blue)](https://www.terraform.io/) 
[![AWS](https://img.shields.io/badge/AWS-Cloud-orange)](https://aws.amazon.com/) 
[![Docker](https://img.shields.io/badge/Docker-Container-blue)](https://www.docker.com/) 
[![GitHub Actions](https://img.shields.io/badge/CI/CD-GitHub%20Actions-green)](https://github.com/features/actions)

---
# flask-ecs-cicd

## Project Title & Description
**flask-ecs-cicd** is a full DevOps project that deploys a Flask web application on **AWS ECS Fargate** using **Terraform** for infrastructure management and **GitHub Actions** for CI/CD automation. The project demonstrates a secure, scalable, and reproducible environment where code changes automatically trigger deployment. The architecture follows a two-tier design: a public subnet hosts the ECS service running the containerized Flask app, and a private subnet is prepared for future internal services or databases. Security groups, IAM roles, and networking are configured following best practices for least-privilege access.

---

## Features
- Containerized Flask application using Docker  
- Infrastructure as code with Terraform (VPC, subnets, ECS, ECR, security groups)  
- Automated CI/CD pipeline using GitHub Actions  
- Secure AWS deployment with proper IAM roles and network isolation  
- Fully reproducible and portfolio-ready DevOps workflow  

---

## Prerequisites
- AWS account with IAM credentials capable of managing ECS, ECR, VPC, and Terraform-managed resources  
- Docker installed locally  
- Terraform installed  
- Git installed  

---

## Installation / Getting Started
1. Clone the repository:  
```bash
git clone https://github.com/<your-username>/flask-ecs-cicd.git
cd flask-ecs-cicd
```

2. Configure AWS CLI:

aws configure


3. Set GitHub secrets for CI/CD (if using GitHub Actions):

AWS_ACCESS_KEY_ID

AWS_SECRET_ACCESS_KEY

## Local Development / Usage

To test the Flask app locally:

docker build -t flask-app .
docker run -p 5000:5000 flask-app


Visit http://localhost:5000 to confirm the app works.

## Project Structure(Tree) 
app1/
├── Dockerfile
├── app.py
├── requirements.txt
├── terraform/
│ ├── main.tf
│ ├── provider.tf
│ └── variables.tf
├── .github/
│ └── workflows/
│ └── deploy.yml
└── README.md


## CI/CD Pipeline / Deployment

GitHub Actions workflow triggers on every push to main

Builds Docker image and pushes it to AWS ECR

Applies Terraform to deploy or update the ECS service automatically

Workflow requires GitHub secrets for AWS credentials

To deploy manually with Terraform:

- cd terraform
- terraform init
- terraform apply


Type yes when prompted. Once deployed, the ECS service runs the container, accessible via the public IP of the task.


## Environment Variables

No specific environment variables are required for this project beyond AWS credentials for deployment:

- AWS_ACCESS_KEY_ID

- AWS_SECRET_ACCESS_KEY

Additional environment variables for Flask (optional):

- FLASK_ENV=development for local testing

- PORT=5000 if you want to customize the container port

- 
