# DevOps Labs

Core hands-on labs for learning DevOps: Git, Docker, Linux on AWS, CI/CD with Jenkins and GitHub Actions, Ansible, Terraform, Azure, Kubernetes, monitoring, and a capstone that connects them.

Each lab has a goal, the commands or console steps, and a **done when** check. Delete any paid cloud resources the same day.

## Topic Index

| Section | Topic | Key Labs |
|---------|-------|----------|
| A | Git and Networking | 1, 2, 3 |
| B | Docker | 4, 5, 7, 11, 15, 16 |
| C | Linux Web Servers on AWS EC2 | 17, 19, 20, 23, 26, 27, 31, 32 |
| D | AWS Developer Tools and Serverless | 33, 34, 35, 36 |
| E | Jenkins CI/CD | 41, 42, 44, 45, 46, 47, 48 |
| F | Ansible | 49, 50, 52, 53, 58 |
| G | Azure | 62, 63, 64, 66, 67, 68 |
| H | Azure DevOps and Containers | 70, 71, 72, 73 |
| I | Kubernetes and Helm | 75, 76, 78 |
| J | Monitoring | 79, 80, 81, 82, 83 |
| K | Resume Gap Labs | 84, 88, 89, 90, 91, 93, 95, 96, 97, 98, 99, 100 |
| L | Advanced Labs | 101, 103, 104, 105, 107, 110, 111 |

## Prerequisites

- Ubuntu machine or VM with Bash
- Git and a GitHub account (SSH key added to GitHub)
- Docker
- AWS account and AWS CLI (`aws configure`)
- Optional, per section: Azure CLI, Terraform, kubectl, Minikube, Helm, Java 11, Node.js 20

Verify your tools:

```bash
git --version
docker --version
aws --version
terraform -version
kubectl version --client
```

## Ground Rules

- **Cost:** Delete paid resources the same day.
- **Secrets:** Never commit passwords, access keys, or tokens. Use placeholders such as `<PASSWORD>` and store real values in environment variables, AWS Secrets Manager, Azure Key Vault, or CI secrets.
- **Ports:** Open only what a lab needs. Avoid `0.0.0.0/0` on SSH, and close temporary rules afterward.

## How to Work a Lab

1. Read the goal and confirm the dependencies.
2. Run the steps in order and save every command that works.
3. Record every error and its fix.
4. Confirm the **done when** condition.
5. Delete the resources the lab created.
6. Commit your notes and code to your repo.

## Repository Layout
