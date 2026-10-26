# Terraform Docker Infrastructure

## Objective
Provision a local Docker container using Infrastructure as Code (IaC) with Terraform.

## Tools
- Terraform
- Docker Engine
- Docker provider: `kreuzwerker/docker`
- Nginx Alpine image

## What I implemented
- Configured the Docker provider.
- Created an Nginx Docker image resource.
- Provisioned a Docker container using Terraform.
- Mapped local port 8085 to container port 80.
- Reviewed the execution plan and Terraform state.
- Destroyed the container using Terraform.

## Commands executed
```bash
terraform init
terraform fmt
terraform validate
terraform plan
terraform apply
terraform state list
terraform state show docker_container.nginx
terraform destroy
```


### 1. What is Infrastructure as Code (IaC)?
IaC is the practice of defining and managing infrastructure using configuration files instead of creating resources manually.

### 2. How does Terraform work?
Terraform reads configuration files, uses providers to communicate with infrastructure APIs, creates an execution plan, applies approved changes, and records resource information in state.

### 3. What is a Terraform state file?
The state file records the resources Terraform manages and their attributes. Terraform uses it to compare the configuration with the tracked infrastructure.

### 4. What is the difference between plan and apply?
`terraform plan` previews proposed changes. `terraform apply` executes the changes after approval, unless approval is configured to be automatic.

### 5. What are Terraform providers?
Providers are plugins that allow Terraform to interact with platforms and APIs, such as Docker, AWS, and Azure.

### 6. What is a resource dependency?
A resource dependency describes which resources must be created or managed before others. Terraform automatically infers dependencies when one resource references another.

### 7. How do you handle secret variables?
Use environment variables, a secret manager, or secure CI/CD credentials. Do not commit secrets or sensitive state files to Git.

### 8. What are the benefits of Terraform?
- Repeatable infrastructure provisioning
- Version-controlled configuration
- Previewing changes before applying them
- Consistent environments
- Easier collaboration and infrastructure cleanup

## Execution Evidence
See the `logs/` directory for the execution logs.

## Cleanup
The Nginx container was removed using `terraform destroy`.
# terraform-docker-iac
