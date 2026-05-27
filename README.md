---

# 📁 terraform-aws-ec2 (Complete Project)

---

## 📌 Project Structure

```text id="k7q1ab"
terraform-aws-ec2/
│
├── provider.tf
├── variables.tf
├── main.tf
├── outputs.tf
├── terraform.tfvars
└── README.md
```

---

## ⚙️ provider.tf

```hcl id="p3v9wx"
provider "aws" {
  region = var.region
}
```

---

## 📦 variables.tf

```hcl id="t6m2kc"
variable "region" {
  description = "AWS region"
  default     = "ap-south-1"
}

variable "instance_type" {
  description = "EC2 instance type"
  default     = "t2.micro"
}

variable "ami_id" {
  description = "AMI ID for EC2"
  default     = "ami-0c55b159cbfafe1f0"
}
```

---

## 🖥️ main.tf

```hcl id="r8k4zn"
resource "aws_instance" "devops_ec2" {
  ami           = var.ami_id
  instance_type = var.instance_type

  tags = {
    Name = "Terraform-EC2-DevOps"
  }
}
```

---

## 📤 outputs.tf

```hcl id="x9j2lm"
output "instance_id" {
  value = aws_instance.devops_ec2.id
}

output "public_ip" {
  value = aws_instance.devops_ec2.public_ip
}
```

---

## 🧾 terraform.tfvars

```hcl id="v2n7qp"
region        = "ap-south-1"
instance_type = "t2.micro"
```

---

# 📘 README.md (Final)

````md id="w5c1sd"
# Terraform AWS EC2 Deployment

## 📌 Project Overview
This project demonstrates Infrastructure as Code (IaC) using Terraform to create an AWS EC2 instance automatically.

Instead of manually creating resources in AWS console, Terraform is used to provision infrastructure using code.

---

## 🎯 Objective
- Learn Infrastructure as Code (IaC)
- Automate AWS EC2 creation
- Understand Terraform workflow
- Practice AWS provider configuration

---

## 🛠️ Technologies Used
- Terraform
- AWS EC2
- IAM (Access Keys)
- Linux (Ubuntu)
- SSH

---

## 📁 Project Structure
terraform-aws-ec2/
│
├── provider.tf
├── variables.tf
├── main.tf
├── outputs.tf
├── terraform.tfvars
└── README.md

---

## ⚙️ Steps to Deploy

### 1. Initialize Terraform
```bash
terraform init
````

### 2. Validate Configuration

```bash
terraform validate
```

### 3. Plan Deployment

```bash
terraform plan
```

### 4. Apply Changes

```bash
terraform apply
```

Type `yes` when prompted.

---

### 5. Destroy Infrastructure (Optional)

```bash
terraform destroy
```

---

## ☁️ What This Creates

* AWS EC2 instance
* Public IP address
* Instance ID output

---

## 🔐 Prerequisites

* AWS account
* IAM user with EC2 permissions
* AWS CLI configured
* Terraform installed

---

## 📚 Learning Outcomes

* Terraform basics
* AWS EC2 provisioning
* Infrastructure as Code workflow
* Variables and outputs
* DevOps automation fundamentals

---

## 👩‍💻 Author

MSc Computer Science (1st Year)
Aspiring DevOps Engineer
Hands-on with AWS, Linux, Docker, Kubernetes & Terraform

---

## 📜 License

This project is for learning purposes.

```
