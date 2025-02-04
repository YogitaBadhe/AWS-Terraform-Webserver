# 🚀 Launch and Configure a Webserver using Terraform

This guide provides a step-by-step approach to launching, connecting to, and configuring a webserver on AWS using Terraform. You'll learn how to configure Terraform, manage AWS resources, and ensure a successful deployment.

---

## ✅ Prerequisites
Before getting started, ensure you have the following installed and configured:

- 🛠 **Terraform** - Installed and configured.
- ☁️ **AWS CLI** - Installed and configured with your access and secret keys using:
  ```bash
  aws configure
  ```
- 🔧 **Git** - Installed to manage your Terraform code repository.

---

## 📌 Step-by-Step Guide

### 1️⃣ Launch EC2 Instance 🏗️
Begin by launching an EC2 instance via the AWS Management Console or using a predefined Terraform configuration.

### 2️⃣ Connect to EC2 Instance 🔗
Connect to your EC2 instance securely via SSH using the appropriate key pair.

### 3️⃣ Install Terraform and Dependencies 🌍
If Terraform is not already installed, follow the installation steps. Also, ensure that AWS CLI is properly set up:
```bash
# Install Terraform (if not installed)
# Configure AWS CLI
aws configure
```

### 4️⃣ Install Git 🛠️
Install Git on your EC2 instance to manage your Terraform configuration files:
```bash
sudo yum install git -y
git --version
git config --global user.name "your_username"
git config --global user.email "your_email@example.com"
```

### 5️⃣ Clone the Repository 📂
Clone the repository containing the Terraform configurations:
```bash
git clone https://github.com/YogitaBadhe/AWS-Terraform-Webserver.git
cd AWS-Terraform-Webserver
```
Alternatively, create the project files manually using PowerShell:
```powershell
mkdir terraformproject
cd .\terraformproject\
New-Item main.tf
New-Item variables.tf
code .
mkdir aws
cd aws
mkdir aws_keys
cd .\aws_keys\
```

### 6️⃣ Create a Key Pair 🔑
Create an AWS key pair named `mywebserver.pem` through the AWS Management Console. Save it in the `aws/aws_keys/` directory and set proper permissions:
```bash
chmod 400 aws/aws_keys/mywebserver.pem
```

### 7️⃣ Update Terraform Configuration 📜
Modify the `main.tf` file to include:
- AWS region settings.
- VPC ID, Subnet ID, and AMI ID.
- Key pair name for SSH access.

Also, update `variables.tf` to include the key pair name.

### 8️⃣ Initialize and Apply Terraform Configuration ⚙️
Run the following Terraform commands to deploy your resources:
```bash
terraform init
terraform validate
terraform fmt
terraform plan
terraform apply
```

### 9️⃣ Verify Deployment 🔍
Once Terraform completes the deployment, retrieve the public IP address of the instance and verify the webserver by accessing it via a web browser.

### 🔟 Clean Up 🗑️
To remove all deployed resources, run:
```bash
terraform destroy
```

### 1️⃣1️⃣ Commit and Push Code 💾
Save your changes and push them to a GitHub repository:
```bash
git add .
git commit -m "Initial commit"
git push origin main
```
For private repositories, use your GitHub token:
```bash
git push https://token@github.com/username/terraform-webserver.git
```

---

🎉 **Congratulations!** You've successfully deployed and configured a webserver on AWS using Terraform! 🚀


