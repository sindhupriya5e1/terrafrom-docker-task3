# 🚀 Terraform Docker – Task 3

## 📌 Task 3: Infrastructure as Code with Terraform

### 🎯 Objective

The objective of this task is to use **Terraform Infrastructure as Code (IaC)** to provision and manage an **Nginx Docker container** locally.

In this task, Terraform is used to:

* Configure the Docker provider
* Pull the Nginx Docker image
* Create an Nginx container
* Map the Docker container port `80` to host port `8082`
* Verify the running container
* Access the Nginx application through a web browser

---

## 🛠️ Technologies Used

* **Terraform**
* **Docker**
* **Docker Desktop**
* **Nginx**
* **PowerShell**
* **Windows**

---

# 📁 Project Structure

```text
terraform-docker/
│
├── main.tf
├── README.md
├── execution-logs.txt
├── .terraform.lock.hcl
├── .gitignore
└── screenshots/
```

---

# 🔹 Step 1: Install and Verify Docker

First, Docker Desktop was installed and started.

Docker installation was verified using:

```bash
docker --version
```

Docker was successfully available on the system.

---

# 🔹 Step 2: Install and Verify Terraform

Terraform was installed and verified using:

```bash
terraform --version
```

Terraform was successfully installed and ready to use.

---

# 🔹 Step 3: Create the Terraform Project

A project folder named:

```text
terraform-docker
```

was created.

The Terraform configuration file was created as:

```text
main.tf
```

---

# 🔹 Step 4: Configure Docker Provider

The `main.tf` file was created to configure Terraform with Docker.

The configuration defines:

* Docker provider
* Nginx Docker image
* Nginx container
* Port mapping

The Nginx container exposes:

```text
Host Port:      8082
Container Port: 80
```

Therefore, the application can be accessed using:

```text
http://localhost:8082
```

---

# 🔹 Step 5: Initialize Terraform

Terraform was initialized using:

```bash
terraform init
```

This downloaded and initialized the required Docker provider.

### Result

```text
Terraform initialization: SUCCESS
```

---

# 🔹 Step 6: Validate Terraform Configuration

The Terraform configuration was checked using:

```bash
terraform validate
```

Expected output:

```text
Success! The configuration is valid.
```

This confirmed that the Terraform configuration was syntactically correct.

---

# 🔹 Step 7: Create Terraform Execution Plan

Next, the infrastructure plan was generated using:

```bash
terraform plan
```

Terraform displayed the resources that would be created.

The planned resources included:

* Nginx Docker image
* Nginx Docker container

---

# 🔹 Step 8: Apply Terraform Configuration

The infrastructure was created using:

```bash
terraform apply
```

Terraform asked for confirmation.

```text
yes
```

was entered to continue.

Terraform then created the Docker infrastructure.

---

# 🔹 Step 9: Port Conflict Issue

During the initial deployment, host port `8080` was already being used.

The running Docker containers were checked using:

```bash
docker ps
```

Port usage was also checked using:

```bash
netstat -ano | findstr :8080
```

Instead of stopping the existing service, the Terraform configuration was modified to use:

```text
8082
```

Final port mapping:

```text
localhost:8082 → Nginx container:80
```

---

# 🔹 Step 10: Verify Docker Container

After running Terraform successfully, the running containers were checked using:

```bash
docker ps
```

The Terraform-managed container appeared as:

```text
terraform-nginx
```

with the port mapping:

```text
0.0.0.0:8082->80/tcp
```

This confirmed that the container was running successfully.

---

# 🔹 Step 11: Browser Verification

The deployment was finally tested through a web browser.

The following URL was opened:

```text
http://localhost:8082
```

The **Nginx Welcome Page** was displayed successfully.

This confirmed that:

* Docker container was running
* Nginx was running
* Port mapping was working
* Terraform deployment was successful

---

# 📸 Screenshots

## 1. Terraform Project Setup

Screenshot showing the Terraform project folder and files.

![Project Setup](screenshots/project-setup.png)

---

## 2. Terraform Initialization

Screenshot showing:

```bash
terraform init
```

![Terraform Init](screenshots/terraform-init.png)

---

## 3. Terraform Validation

Screenshot showing:

```bash
terraform validate
```

![Terraform Validate](screenshots/terraform-validate.png)

---

## 4. Terraform Plan

Screenshot showing:

```bash
terraform plan
```

![Terraform Plan](screenshots/terraform-plan.png)

---

## 5. Terraform Apply

Screenshot showing:

```bash
terraform apply
```

![Terraform Apply](screenshots/terraform-apply.png)

---

## 6. Docker Container Running

Screenshot showing:

```bash
docker ps
```

![Docker Container](screenshots/docker-ps.png)

---

## 7. Nginx Browser Verification

Screenshot showing the Nginx Welcome Page at:

```text
http://localhost:8082
```

![Nginx](screenshots/nginx-browser.png)

---

# 📊 Final Result

| Step                 | Status       |
| -------------------- | ------------ |
| Docker Setup         | ✅ Successful |
| Terraform Setup      | ✅ Successful |
| Terraform Init       | ✅ Successful |
| Terraform Validate   | ✅ Successful |
| Terraform Plan       | ✅ Successful |
| Terraform Apply      | ✅ Successful |
| Docker Container     | ✅ Running    |
| Nginx Deployment     | ✅ Successful |
| Browser Verification | ✅ Successful |

---

# 🔄 Complete Workflow

```text
Create Terraform Project
          ↓
Configure Docker Provider
          ↓
terraform init
          ↓
terraform validate
          ↓
terraform plan
          ↓
terraform apply
          ↓
Docker Nginx Container Created
          ↓
Port 8082 → Container Port 80
          ↓
docker ps
          ↓
Open localhost:8082
          ↓
Nginx Welcome Page
```

---

# 🎓 What I Learned

Through this task, I learned how to use **Terraform as an Infrastructure as Code tool** to manage Docker resources.

Key learnings:

* Terraform project initialization
* Terraform configuration
* Docker provider configuration
* Terraform validation
* Terraform planning
* Terraform resource provisioning
* Docker container management
* Port mapping
* Troubleshooting port conflicts
* Verifying infrastructure deployment

---

# ✅ Conclusion

Task 3 was successfully completed by provisioning an **Nginx Docker container using Terraform**.

The complete Infrastructure as Code workflow was implemented from configuration to deployment and browser verification.

**Terraform → Docker → Nginx → Port Mapping → Browser Verification**

This task demonstrates the basic practical workflow of using Terraform to declaratively provision and manage containerized infrastructure.
