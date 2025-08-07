# 🚀 Terraform Docker Nginx

This project demonstrates how to use **Terraform** to provision a local **Docker container** running the Nginx web server. It is part of a DevOps internship task focused on learning **Infrastructure as Code (IaC)**.

---

## 📌 What is Infrastructure as Code (IaC)?

**Infrastructure as Code (IaC)** is a DevOps practice where you manage and provision infrastructure (like containers, servers, networks) using code instead of doing it manually. Tools like Terraform make it possible.

---

## 🧰 Tools Required

Before starting, install the following:

### ✅ 1. [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- Required to run containers on your local machine.
- After installation, **launch Docker Desktop** and ensure it is running.

### ✅ 2. [Terraform](https://developer.hashicorp.com/terraform/downloads)
- Used to automate the creation of infrastructure.
- After downloading:
  - Extract `terraform.exe`
  - Move it to a folder (e.g., `C:\terraform`)
  - Add that folder to your **System PATH**
  - Test by running:
    ```powershell
    terraform version
    ```

---

## 📁 Project Structure
terraform-docker/
│
├── main.tf # Terraform configuration file
├── apply_log.txt # Log output after running terraform apply
├── destroy_log.txt # Log output after running terraform destroy
└── README.md # This file

## 📝 What This Project Does

- Uses Terraform to pull the official Nginx Docker image
- Creates a Docker container from that image
- Maps Nginx port 80 (internal) to port 8080 on your local machine
- Runs the container so you can visit Nginx on your browser

---

## 🚀 Step-by-Step Guide

### 📂 Step 1: Clone the Repository (or Create a Folder)

If you're following along manually, create a folder:

```powershell
mkdir terraform-docker
cd terraform-docker

1. Create a file named main.tf
<img width="1919" height="1009" alt="image" src="https://github.com/user-attachments/assets/e8e136fd-2816-4a9c-a73c-6434dbbd7f54" />

2. terraform init
3. terraform plan
4. terraform apply                       
  Type yes when prompted.
  This will:
  Pull the nginx image
  Create and run the container
5. Test Nginx: http://localhost:8080
<img width="1917" height="931" alt="image" src="https://github.com/user-attachments/assets/03fd7a26-4b78-4592-b11f-5e3dbfec03ed" />
6. Destroy the Infrastructure: terraform destroy
7. Save Logs (Optional but Good Practice)
   terraform apply -auto-approve | tee apply_log.txt
  terraform destroy -auto-approve | tee destroy_log.txt
