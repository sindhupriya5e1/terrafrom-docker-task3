# Terraform Docker Deployment – Task 3

## 📌 Project Overview

This project demonstrates how to use **Terraform to provision and manage Docker resources**.

In this task, Terraform is used to:

- Initialize the Terraform project
- Validate the Terraform configuration
- Create an execution plan
- Pull/create an Nginx Docker image
- Create an Nginx Docker container
- Verify the running Docker container
- Verify Terraform-managed resources using Terraform State
- Destroy the created resources using Terraform

---

## 🛠️ Technologies Used

- Terraform
- Docker
- Nginx
- Command Prompt / Terminal
- Git & GitHub

---

# 🚀 Task 3 – Step-by-Step Implementation

## Step 1: Terraform Initialization and Validation

First, the Terraform project directory was opened in Command Prompt.

The Terraform configuration was initialized using:

```bash
terraform init
Terraform downloaded and installed the required Docker provider.

After successful initialization, the configuration was validated using:

terraform validate
The validation was successful, which confirmed that the Terraform configuration was syntactically correct and ready for planning.

Commands Used
terraform init
terraform validate
Result
Terraform initialized successfully.

Docker provider was installed.

Terraform configuration was successfully validated.

Step 2: Terraform Plan
After successful initialization and validation, the Terraform execution plan was generated using:

terraform plan
Terraform analyzed the configuration and displayed the resources that would be created.

The plan showed:

An Nginx Docker image to be created/managed.

An Nginx Docker container to be created.

Port mapping from the Docker container to the host.

The plan displayed:

Plan: 2 to add, 0 to change, 0 to destroy.
This means Terraform planned to create two resources.

Resources
docker_image.nginx
docker_container.nginx
The Nginx container was configured with port:

External: 8080
Internal: 80
Protocol: TCP
Step 3: Terraform Apply
After reviewing the Terraform plan, the infrastructure was created using:

terraform apply
Terraform displayed the planned actions and asked for confirmation.

The following value was entered:

yes
Terraform then created the required Docker resources.

The following resources were created:

docker_image.nginx
docker_container.nginx
The command completed successfully with:

Apply complete! Resources: 2 added, 0 changed, 0 destroyed.
Result
The Nginx Docker image was created and the Nginx Docker container was successfully started.

🐳 Step 4: Verify Docker Container and Terraform State
After Terraform successfully created the resources, the running Docker containers were checked using:

docker ps
The command displayed the Nginx container as running.

The port mapping was also visible:

0.0.0.0:8080 -> 80/tcp
This confirms that port 8080 on the host was mapped to port 80 inside the Nginx container.

The Terraform-managed resources were then checked using:

terraform state list
The Terraform state showed:

docker_image.nginx
docker_container.nginx
This confirms that Terraform was tracking both Docker resources through its state.

🗑️ Step 5: Terraform Destroy
After verifying the deployment, the resources were removed using:

terraform destroy
Terraform displayed the resources that would be destroyed and asked for confirmation.

The following value was entered:

yes
Terraform then destroyed:

Nginx Docker container

Nginx Docker image

The operation completed successfully with:

Destroy complete! Resources: 2 destroyed.
This confirms that Terraform successfully removed all resources that it had created.

📂 Terraform Workflow
The complete workflow followed in this task was:

Terraform Project
       ↓
terraform init
       ↓
terraform validate
       ↓
terraform plan
       ↓
terraform apply
       ↓
Docker Image Created
       ↓
Docker Container Created
       ↓
docker ps
       ↓
terraform state list
       ↓
terraform destroy
       ↓
Resources Removed
📸 Screenshots
1. Terraform Init & Validate
The first screenshot shows successful Terraform initialization and validation.

Commands:

terraform init
terraform validate
Result:

Terraform has been successfully initialized!
Success! The configuration is valid.
2. Terraform Plan
The second screenshot shows the Terraform execution plan.

The plan indicates:

Plan: 2 to add, 0 to change, 0 to destroy.
Resources planned:

docker_image.nginx
docker_container.nginx
3. Terraform Apply
The third screenshot shows the successful Terraform apply operation.

Terraform created the Nginx Docker image and container.

Result:

Apply complete! Resources: 2 added, 0 changed, 0 destroyed.
4. Docker Container & Terraform State
The fourth screenshot shows:

docker ps
and:

terraform state list
The Docker container is shown as running, and Terraform state contains:

docker_image.nginx
docker_container.nginx
5. Terraform Destroy
The final screenshot shows the destruction of the Terraform-managed resources.

Command:

terraform destroy
Result:

Destroy complete! Resources: 2 destroyed.
📊 Task 3 Result
Step	Command	Result
1	terraform init	Successfully initialized
2	terraform validate	Configuration valid
3	terraform plan	2 resources planned
4	terraform apply	2 resources created
5	docker ps	Nginx container verified
6	terraform state list	Resources verified in state
7	terraform destroy	2 resources destroyed
✅ Conclusion
Task 3 successfully demonstrated the complete Terraform workflow for managing Docker resources.

Terraform was initialized and validated first. Then an execution plan was generated and applied to create an Nginx Docker image and container. The running container and Terraform state were verified successfully. Finally, terraform destroy was used to remove the resources.

Therefore, the task demonstrates the complete Infrastructure as Code (IaC) lifecycle:

Initialize → Validate → Plan → Apply → Verify → Destroy

**Mee PDF lo unna 5 screenshots order exactly idhe:**  
**01 Init & Validate → 02 Plan → 03 Apply → 04 Docker Container & Terraform State → 05 Destroy.** :contentReference[oaicite:1]{index=1}

GitHub README lo **screenshots kuda visible ga ravali** ante next step lo ee 5 screenshots ni separate files ga arrange chesi, README lo exact `![Screenshot](...)` lines kuda ista.

terraform_task3_screenshots.pdf
