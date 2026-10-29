# DevOps Labs

A hands-on path through Git, Docker, AWS, Jenkins, Ansible, Azure, Kubernetes, and monitoring, ending with a capstone that connects them.

## Labs

### Section A: Git and Networking

- **Lab 1: Git Global Configuration.** Set your name, email, editor, and line-ending behavior.
- **Lab 2: Git SSH Key Setup and Branch Push Workflow.** Authenticate to GitHub with SSH and push a feature branch.
- **Lab 3: IPv4 and IPv6 Addressing and Subnetting.** Read IP addresses, masks, and host ranges.

### Section B: Docker

- **Lab 4: Apache Web Server in a Custom Docker Image.** Build an image from a Dockerfile and serve a page through a port mapping.
- **Lab 5: Node.js Web App Docker Image Pushed to Docker Hub.** Containerize a Node.js app and publish it to a registry.
- **Lab 6: Custom Docker Image with Files and Environment Variables.** Bake files and variables into an image.
- **Lab 7: Sharing Data Between Containers with volumes-from.** Share a volume so one container's files appear in another.
- **Lab 8: Volume Sharing Between Containers Using -v and --volumes-from.** Compare named volumes and mounted directories.
- **Lab 9: Host Directory Mounted into a Container.** Mount a host folder so container files appear on the host.
- **Lab 10: Linking Containers (Jenkins to Ubuntu).** Connect containers by name and read the link variables.
- **Lab 11: Private Docker Registry on localhost:5000.** Run your own registry and push and pull images through it.
- **Lab 12: MongoDB in Docker with mongosh.** Run a database container and open a shell inside it.
- **Lab 13: Apache in a Docker Ubuntu Container.** Install a web server inside a container and expose it on EC2.
- **Lab 14: Jenkins in a Docker Container on Port 8080.** Run Jenkins in Docker and reach it from a browser.
- **Lab 15: Docker Compose Basic Web Setup.** Run several containers from one YAML file.
- **Lab 16: Docker Compose Python Web App with Hit Counter.** Run an app and a service it depends on with Compose.

### Section C: Linux Web Servers on AWS EC2

- **Lab 17: Apache on Ubuntu EC2 with an Elastic IP.** Install Apache on an EC2 instance with a fixed public IP.
- **Lab 18: Node.js App on EC2 with pm2.** Keep a Node.js app running after you log out.
- **Lab 19: Nginx Hosting Two Sites on Different Ports.** Serve two sites from one Nginx server.
- **Lab 20: Nginx with a Domain, Route 53, ALB, SSL, and HTTP-to-HTTPS Redirect.** Put a domain, load balancer, and certificate in front of a site.
- **Lab 21: Windows Server 2022 with IIS on EC2.** Host a static page on Windows IIS.
- **Lab 22: Two Windows IIS Servers Behind an ALB Across Availability Zones.** Balance traffic across servers in two zones.
- **Lab 23: Tomcat 10 on Ubuntu EC2.** Install Tomcat as a systemd service and deploy a site.
- **Lab 24: Static Website on S3 with CloudFront.** Serve S3 content through a CDN.
- **Lab 25: Static Website on S3 with Public Hosting.** Host `index.html` directly from an S3 bucket.
- **Lab 26: Elastic Beanstalk Node.js Deployment from a Zip File.** Deploy an app package to a managed environment.
- **Lab 27: CloudFormation S3 Bucket with Parameters, Update, and Delete.** Deploy, change, and remove a stack from the CLI.
- **Lab 28: CloudFormation Basic S3 Bucket Deployment.** Deploy a template with default values.
- **Lab 29: CloudFormation S3 Bucket with a Named Parameter.** Override a template parameter from the command line.
- **Lab 30: Change EC2 Instance Type with a Script.** Run an AWS sample script that resizes an instance.
- **Lab 31: EC2 Stop or Terminate Alert with CloudWatch Events and SNS.** Get an email when an instance stops.
- **Lab 32: Lambda Container Image with API Gateway HTTP API.** Run a container image as a Lambda function behind an HTTP endpoint.

### Section D: AWS Developer Tools and Serverless

- **Lab 33: IAM User and SSH Config for CodeCommit.** Clone a CodeCommit repo over SSH with an IAM user.
- **Lab 34: CodeBuild Static Site from CodeCommit to S3.** Build a site automatically and publish it to S3.
- **Lab 35: Lambda Image Resize on S3 Upload.** Resize images automatically when they land in a bucket.
- **Lab 36: S3 Upload Logging to DynamoDB with Lambda.** Record every S3 upload in a DynamoDB table.
- **Lab 37: Lambda Python Code for S3-to-DynamoDB Logging.** Provide the function code used in Lab 36.
- **Lab 38: Static Website on Lambda via API Gateway REST API.** Serve a website from a Lambda function.
- **Lab 39: EC2 AMI, Auto Scaling Group, Load Balancer, and Load Test.** Scale instances on CPU and test them under load.
- **Lab 40: Windows Auto Scaling Group with CPU-Based Scaling.** Scale Windows instances on CPU load.

### Section E: Jenkins CI/CD

- **Lab 41: Jenkins Installation on Windows, Ubuntu, and EC2.** Install Jenkins and finish the setup wizard.
- **Lab 42: Jenkins Freestyle Hello World Job.** Run a simple shell job and read its output.
- **Lab 43: Jenkins Parameterized Freestyle Job.** Pass values and files into a job at build time.
- **Lab 44: GitHub Integration with Personal Access Token and Webhook Trigger.** Build automatically on every push.
- **Lab 45: Jenkins Pipeline with an Inline Script.** Define a pipeline in the Jenkins UI.
- **Lab 46: Jenkinsfile from Source Control.** Keep the pipeline definition in the repo.
- **Lab 47: Jenkins Docker Build and Push to ECR.** Build an image in Jenkins and push it to AWS ECR.
- **Lab 48: Jenkins Node.js Pipeline with NodeJS Tool, Credentials, and Artifacts.** Build Node.js, use a secret safely, and archive output.

### Section F: Ansible

- **Lab 49: Install Ansible on Ubuntu via PPA.** Install Ansible from the official repository.
- **Lab 50: Ansible Inventory and Ping Test.** Define hosts and confirm connectivity.
- **Lab 51: Ansible Ad-hoc Commands.** Run one-line commands for reboots, files, packages, and facts.
- **Lab 52: Ansible Playbook to Install Apache.** Install and start Apache from a playbook.
- **Lab 53: Ansible Playbook to Install and Start Tomcat.** Deploy Tomcat from a playbook.
- **Lab 54: Ansible Variables, Blocks, and Tags Overview.** Use variables and group tasks into blocks.
- **Lab 55: Ansible Conditionals with when.** Run a task only when a condition is true.
- **Lab 56: Ansible Loops with register and stdout_lines.** Loop over command output and act on each item.
- **Lab 57: Ansible Exception Handling with block, rescue, and always.** Handle failures like try, catch, and finally.
- **Lab 58: Apache Role-Based Playbook.** Organize Apache setup into reusable roles.
- **Lab 59: Tomcat Role-Based Playbook.** Organize Tomcat setup into reusable roles.
- **Lab 60: Ansible Role Structure with ansible-galaxy.** Generate and understand the standard role layout.

### Section G: Azure

- **Lab 61: Azure Core Concepts Checklist.** Learn the main Azure building blocks before deploying.
- **Lab 62: Azure VM Data Disk Attach, Partition, and Mount.** Add a data disk and mount it permanently.
- **Lab 63: Azure Resource Deployment with an ARM Template.** Deploy resources from a JSON template.
- **Lab 64: Terraform Workspaces (qa and default).** Keep separate state for each environment.
- **Lab 65: Scale an Azure SQL Database with an Automation Runbook.** Change a database's tier with a PowerShell runbook.
- **Lab 66: Azure Function from a Docker Hub Container Image.** Run a containerized app on Azure Functions.
- **Lab 67: VPN Gateway with Point-to-Site Entra ID Authentication.** Connect a laptop to an Azure network.
- **Lab 68: Private Endpoints with Private DNS for Storage and SQL.** Reach SQL and storage through private IPs.
- **Lab 69: VNet Peering and Availability Sets vs Availability Zones.** Compare network connections and failure isolation.

### Section H: Azure DevOps and Containers

- **Lab 70: ACR and Azure Container Instance with Nginx.** Push an image to Azure Container Registry and run it.
- **Lab 71: Azure DevOps Docker Registry Service Connection and Build Pipeline.** Build an image and push it to ACR from a pipeline.
- **Lab 72: Azure DevOps Deploy Stage to Azure Container Instance.** Add a deploy stage to the pipeline.
- **Lab 73: Split Build and Release Pipelines to Azure Container Instance.** Separate building from deploying with an artifact.
- **Lab 74: Docker Compose on ACI with a Docker Context.** Deploy a multi-container app to Azure with Compose.

### Section I: Kubernetes, Helm, and Managed Clusters

- **Lab 75: Kubernetes Sample App Deployment with kubectl.** Deploy an app and reach it through a LoadBalancer.
- **Lab 76: EKS Cluster, Node Group, IAM Roles, and kubeconfig.** Create a managed Kubernetes cluster on AWS.
- **Lab 77: AKS Image Pull Secret, Service Principal, and Pipelines.** Let AKS pull images from ACR and deploy with Helm pipelines.
- **Lab 78: Prometheus and Grafana on Kubernetes with Helm.** Install monitoring tools on a cluster with Helm.

### Section J: Monitoring with Prometheus, Node Exporter, and Grafana

- **Lab 79: Prometheus Installation on Ubuntu EC2.** Install Prometheus and run it as a service.
- **Lab 80: Node Exporter Installation and Scrape Configuration.** Collect machine metrics and add them to Prometheus.
- **Lab 81: PromQL Queries, Recording Rules, and Alerting.** Query metrics, store calculations, and define alerts.
- **Lab 82: Alertmanager with Gmail SMTP Notifications.** Send an email when an alert fires.
- **Lab 83: Grafana Installation, Prometheus Data Source, and Node Exporter Dashboard.** Visualize metrics in dashboards.

### Section K: Resume Gap Labs

- **Lab 84: GitHub Actions CI/CD Pipeline.** Build, test, and push a Docker image on every push.
- **Lab 85: Python AMI Cleanup Script with boto3.** Find and remove old AMIs with a dry-run-first script.
- **Lab 86: Menu-Driven Linux Admin CLI.** Build a Bash tool for user management and backups.
- **Lab 87: Bash Health Monitor with Threshold Alerts.** Log CPU, memory, and disk usage on a schedule.
- **Lab 88: Terraform Project with VPC, EC2, S3, Remote State, and Dev/QA.** Build an AWS environment from code with locked remote state.
- **Lab 89: Docker Compose Four-Service Application.** Run a proxy, API, database, and cache together.
- **Lab 90: Deploy the Four-Service Application to Kubernetes on Minikube.** Run the same app on a local cluster with Deployments and Services.
- **Lab 91: GitOps with Argo CD.** Deploy from Git so cluster state follows the repo.
- **Lab 92: PostgreSQL and MySQL in Containers with Persistent Data.** Keep database data across container restarts.
- **Lab 93: Nginx Reverse Proxy with Let's Encrypt SSL.** Serve an app over HTTPS with a free certificate.
- **Lab 94: CloudWatch CPU Alarm with SNS Email Notification.** Get an email when CPU stays high.
- **Lab 95: IAM Least-Privilege Policy.** Grant access to one bucket and prove other actions are denied.
- **Lab 96: Linux Server Hardening.** Disable password and root SSH logins, enable a firewall, and block brute force.
- **Lab 97: Secrets Management.** Store secrets in AWS Secrets Manager or Azure Key Vault and scan Git for leaks.
- **Lab 98: Git Pull Request Workflow with Branch Protection.** Work on branches and block direct pushes to main.
- **Lab 99: Documentation and Runbooks.** Write a README and a runbook someone else can follow.
- **Lab 100: Build and Update Your CV.** Turn each resume claim into evidence-backed bullets.

### Section L: Advanced Labs

- **Lab 101: Terraform Module Refactor of Lab 88.** Split Terraform into reusable modules without recreating resources.
- **Lab 102: Terraform Import, State Operations, and for_each.** Bring existing resources under management and manage state safely.
- **Lab 103: Terraform Plan on Every Pull Request, with Provider Pinning.** Run format, validate, and plan in CI with OIDC.
- **Lab 104: Kubernetes Resource Requests, Limits, Probes, and Autoscaling.** Add health checks and scale pods on CPU.
- **Lab 105: Kubernetes Debugging Drills.** Diagnose CrashLoopBackOff, ImagePullBackOff, and Pending pods.
- **Lab 106: Kubernetes RBAC, NetworkPolicy, and Ingress with TLS.** Limit permissions, restrict traffic, and serve HTTPS.
- **Lab 107: Image Scanning, Dependency Audit, and SBOM in CI.** Fail builds on serious vulnerabilities and produce an SBOM.
- **Lab 108: Policy-as-Code on Terraform Plans with Conftest.** Block risky infrastructure changes automatically.
- **Lab 109: Pipeline Metrics (DORA).** Measure lead time, failure rate, and recovery time from your pipeline.
- **Lab 110: Capstone: Commit to Running Pod.** Connect CI, security checks, GitOps, Kubernetes, and alerting into one system.
- **Lab 111: Interview Preparation Sessions.** Practice explaining design, debugging, and your projects out loud.


