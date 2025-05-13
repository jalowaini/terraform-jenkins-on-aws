# Jenkins on AWS EC2 with Terraform


## Project Overview

This project automates the setup of a Jenkins server on an EC2 instance using Terraform. It includes networking, compute provisioning, security configurations, and Jenkins auto-installation via shell script.

---

## Tech Stack

- **Terraform** – Infrastructure provisioning
- **AWS EC2** – Virtual server to host Jenkins
- **Jenkins** – CI/CD automation server
- **Bash Script** – Jenkins auto-installation

---

## Directory Structure

```bash
terraform-jenkins-on-aws/
├── main.tf                 # Main infrastructure configuration
├── variables.tf            # Input variable definitions
├── outputs.tf              # Output values (e.g., Jenkins IP)
├── terraform.tfvars        # Sensitive variables like public IP (not pushed to GitHub)
├── jenkins_installation.sh # Script to auto-install Jenkins
└── .gitignore              # Ignored files and directories
```

---

## Deployment Instructions

### 1. Clone the repository

```bash
git clone https://github.com/jalowaini/terraform-jenkins-on-aws.git
cd terraform-jenkins-on-aws
```

### 2. Set your public IP

Create a file named `terraform.tfvars`:

```hcl
my_ip = "<your-current-public-ip>"
```

Get your IP using:

```bash
curl -4 ifconfig.me
```

### 3. Initialize Terraform

```bash
terraform init
```

### 4. Review and apply the infrastructure

```bash
terraform plan
terraform apply
```

### 5. Access Jenkins server

SSH into EC2:

```bash
ssh -i ~/.ssh/MyKey ubuntu@<your-elastic-ip>
```

Retrieve Jenkins admin password:

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Open Jenkins in your browser:

```
http://<your-elastic-ip>:8080
```

---

## Expected Result

A fully automated, browser-accessible Jenkins server running on AWS EC2 with infrastructure provisioned entirely using Terraform.


Output of terraform apply

Jenkins login or dashboard screen

Expected Result
A fully automated, browser-accessible Jenkins server running on AWS EC2 with infrastructure provisioned entirely using Terraform.

---
## 👨‍💻 Author
Built with ❤️ by @jalowaini
