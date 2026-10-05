# Infrastructure as Code (IaC) with Terraform and Docker

## Project Overview

This project demonstrates the implementation of **Infrastructure as Code (IaC)** using **Terraform and Docker**.

The objective of this task was to use Terraform to automatically provision and manage an **Nginx Docker container** instead of creating and managing the container manually.

In this project, Terraform was configured with the **Docker provider** to:

- Download the Nginx Docker image
- Create an Nginx Docker container
- Configure port mapping
- Verify the running container
- Inspect Terraform-managed resources
- Destroy the infrastructure using Terraform

The complete Terraform lifecycle was successfully executed from initialization to destruction.

---

## Objective

The main objective of this task is to understand the basic concepts of **Infrastructure as Code** and learn how Terraform can be used to manage Docker infrastructure.

The complete workflow followed in this project was:

1. Configure Terraform with the Docker provider
2. Initialize the Terraform working directory
3. Format the Terraform configuration
4. Validate the configuration
5. Generate and review the Terraform execution plan
6. Provision the Docker image and container
7. Verify the running Docker container
8. Check Terraform state
9. Destroy the provisioned infrastructure
10. Verify that the resources were removed successfully

---

## Technologies and Tools Used

- **Terraform**
- **Docker Desktop**
- **Docker Engine**
- **Docker Provider for Terraform**
- **Nginx**
- **Windows Command Prompt**
- **Git**
- **GitHub**

---

## Architecture

The project follows this simple infrastructure flow:

```text
                Terraform Configuration
                         |
                         v
                 Terraform Docker Provider
                         |
              +----------+----------+
              |                     |
              v                     v
        Nginx Docker Image    Nginx Docker Container
                                    |
                                    v
                           Port 8080 -> Port 80
                                    |
                                    v
                              Local Machine
Terraform acts as the Infrastructure as Code tool and communicates with Docker through the Docker provider.

Project Implementation
Step 1: Verify Docker Installation
Before starting Terraform, Docker Desktop was installed and running.

The Docker installation was verified using:

docker version
The command successfully displayed the Docker Client and Docker Server information.

This confirmed that Docker was properly installed and available for Terraform to manage.

Step 2: Create Terraform Configuration
A Terraform configuration file named:

main.tf
was created.

The configuration uses the Docker provider and defines two Terraform resources:

Docker Nginx image

Docker Nginx container

The Nginx image used in this project is:

nginx:alpine
The container exposes:

Host Port: 8080
Container Port: 80
Therefore, the Nginx application can be accessed through port 8080 on the local machine.

Step 3: Initialize Terraform
The Terraform working directory was initialized using:

terraform init
Terraform downloaded and configured the required Docker provider.

The initialization completed successfully with:

Terraform has been successfully initialized!
This step prepared the working directory for the remaining Terraform commands.

Step 4: Format Terraform Configuration
The Terraform configuration was formatted using:

terraform fmt
This command ensures that the Terraform configuration follows the standard Terraform formatting style.

Step 5: Validate Terraform Configuration
The configuration was then validated using:

terraform validate
Terraform returned:

Success! The configuration is valid.
This confirmed that the Terraform configuration had no syntax or configuration errors.

Step 6: Create Terraform Execution Plan
Before creating the infrastructure, the expected changes were reviewed using:

terraform plan
Terraform generated an execution plan showing that 2 resources would be created:

1. docker_image.nginx
2. docker_container.nginx
The Docker image was:

nginx:alpine
The container was configured with the following port mapping:

8080 -> 80
The plan was reviewed before applying the changes.

Step 7: Provision Infrastructure Using Terraform
The infrastructure was created using:

terraform apply
Terraform displayed the proposed changes and requested confirmation.

The deployment was approved by entering:

yes
Terraform then successfully created both resources.

The final result was:

Apply complete! Resources: 2 added, 0 changed, 0 destroyed.
This confirmed that the Nginx Docker image and container were successfully provisioned.

Step 8: Verify Docker Container
After Terraform completed the deployment, the running Docker containers were checked using:

docker ps
The Nginx container was displayed as running.

The port mapping was also visible:

0.0.0.0:8080 -> 80/tcp
This confirmed that the container was successfully created and running.

Step 9: Check Terraform State
Terraform keeps track of the resources it manages through its state.

The Terraform state was checked using:

terraform state list
The following resources were listed:

docker_container.nginx
docker_image.nginx
This confirmed that Terraform was successfully tracking both Docker resources.

Step 10: Destroy the Infrastructure
After verification, the infrastructure was removed using:

terraform destroy
Terraform displayed the resources that would be destroyed and requested confirmation.

The destruction was approved by entering:

yes
Terraform successfully removed the resources.

The final result was:

Destroy complete! Resources: 2 destroyed.
Step 11: Verify Resource Cleanup
After destruction, the Terraform state was checked again:

terraform state list
No managed resources remained in the Terraform state.

The Docker containers were also checked using:

docker ps
No running containers were displayed.

This confirmed that the infrastructure created by Terraform had been successfully removed.

Terraform Lifecycle Demonstrated
The complete Terraform lifecycle implemented in this project was:

Configuration
      |
      v
terraform init
      |
      v
terraform fmt
      |
      v
terraform validate
      |
      v
terraform plan
      |
      v
terraform apply
      |
      v
Docker Container Running
      |
      v
terraform state list
      |
      v
terraform destroy
      |
      v
Infrastructure Removed
Terraform Commands Used
Command	Purpose
docker version	Verify Docker installation
terraform init	Initialize Terraform
terraform fmt	Format Terraform configuration
terraform validate	Validate configuration
terraform plan	Preview infrastructure changes
terraform apply	Create infrastructure
docker ps	Verify running Docker containers
terraform state list	View Terraform-managed resources
terraform destroy	Remove infrastructure
Resources Created
Terraform created the following resources:

1. Docker Image
nginx:alpine
2. Docker Container
Nginx container
Port Mapping
Host: 8080
Container: 80
Protocol: TCP
Terraform State
Terraform state is used to keep track of the infrastructure resources managed by Terraform.

In this project, the state contained references to:

docker_image.nginx
docker_container.nginx
The state was checked using:

terraform state list
After running:

terraform destroy
the resources were removed from the Terraform state.

Terraform state files are not included in the GitHub repository because state files may contain infrastructure-related information and should generally not be committed to a public repository.
