# 🚀 AWS Terraform Webserver - Step-by-Step Guide

Welcome to the **AWS Terraform Webserver** setup guide! This document will guide you through the entire process of setting up an AWS EC2 instance as a web server using **Terraform**. 🌐💻

---

## 📌 Prerequisites
Before proceeding, ensure you have the following:
- **AWS Account** ✅
- **IAM User with Administrator Access** ✅
- **Amazon Linux 2 EC2 Instance** ✅
- **Terraform Installed** ✅
- **Git Installed** ✅

---

## 📖 Step 1: Update and Install Required Packages
First, update your Amazon Linux system and install Git:

```sh
sudo yum update -y
sudo yum install git -y
```

Verify Git installation:
```sh
git --version
```

Configure Git with your details:
```sh
git config --global user.name "YogitaBadhe"
git config --global user.email "ybadhe0990@gmail.com"
git config --list
```

---

## 📖 Step 2: Install and Configure Apache Web Server

```sh
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
sudo systemctl status httpd
```

Your webserver is now running! 🚀

---

## 📖 Step 3: Clone the AWS Terraform Webserver Repository

Clone the GitHub repository:
```sh
git clone https://github.com/YogitaBadhe/AWS-Terraform-Webserver.git
ls
cd AWS-Terraform-Webserver/
```

---

## 📖 Step 4: Setup Project Directory Structure

Install the `tree` command to visualize the directory structure:
```sh
sudo yum install tree -y
tree
```

Create directories and navigate into them:
```sh
mkdir aws
cd aws
mkdir aws_keys
cd aws_keys
```

Create and open the **TerraformWebserver.pem** file to store the AWS key credentials:
```sh
sudo touch TerraformWebserver.pem
sudo nano TerraformWebserver.pem  # Paste your .pem key credentials here
```

Create Terraform configuration files:
```sh
sudo touch variable.tf
sudo nano variable.tf  # Paste your variables here

sudo touch main.tf
sudo nano main.tf  # Paste your Terraform script here
```

---

## 📖 Step 5: Configure AWS CLI

Run the following command to set up AWS credentials:
```sh
aws configure
```
Provide the necessary details:
```
Access Key: YOUR_ACCESS_KEY
Secret Access Key: YOUR_SECRET_ACCESS_KEY
Region Code: us-east-1
Output Format: json
```
Verify AWS CLI installation:
```sh
aws --version
```

---

## 📖 Step 6: Setup Web Server Files

Navigate to the webserver directory:
```sh
cd /var/www/html
pwd
ls
```

Create and edit the **index.html** file:
```sh
sudo nano index.html  # Add your website content here
sudo touch index.html
ls
```

---

## 📖 Step 7: Install Terraform on Amazon Linux 2

Run the following commands to install Terraform:
```sh
sudo yum install -y yum-utils shadow-utils
sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo
sudo yum -y install terraform
terraform --version
```

---

## 📖 Step 8: Terraform Workflow

### 🛠 Initialize Terraform
```sh
terraform init
```

### ✅ Validate Configuration
```sh
terraform validate
```

### 🎨 Format Configuration
```sh
terraform fmt
```

### 🔍 Plan Infrastructure
```sh
terraform plan
```

### 🚀 Apply Configuration (Deploy Resources)
```sh
terraform apply -auto-approve
```

### 💥 Destroy Resources (Clean Up)
```sh
terraform destroy -auto-approve
```

---

## 📖 Step 9: Push Changes to GitHub

```sh
git add .
git commit -m "Updated the changes"
git push origin main
```

---

## 🎯 Conclusion
Congratulations! 🎉 You have successfully set up an **AWS Terraform Webserver** using Terraform and Git. Happy coding! 🚀

