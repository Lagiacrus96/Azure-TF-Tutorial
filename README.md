# Azure Infrastructure Deployment with Terraform

This repository contains Terraform configurations to deploy a basic Azure infrastructure consisting of virtual networks, subnets, network interfaces, virtual machines, and network security groups. The infrastructure is designed to demonstrate a simple setup for hosting virtual machines in Azure with both public and private network access.

## Prerequisites

Before you begin, ensure you have the following prerequisites installed:

- Terraform: https://www.terraform.io/downloads.html
- Azure CLI: https://docs.microsoft.com/en-us/cli/azure/install-azure-cli

Additionally, make sure you have an active Azure subscription and appropriate permissions to create Azure resources.

## Usage

1. Clone the repository to your local machine:

   ```
   git clone <repository-url>
   ```

2. Change into the cloned directory:

   ```
   cd <repository-directory>
   ```

3. Initialize Terraform to download provider plugins:

   ```
   terraform init
   ```

4. Review and customize the `main.tf` file to adjust configuration settings such as resource names, locations, and sizes according to your requirements.

5. Optionally, you can create a `terraform.tfvars` file to specify variable values without hardcoding them in the `main.tf` file:

   ```
   # terraform.tfvars

   resource_group_name = "my-resource-group"
   location            = "East US"
   ```

6. Preview the execution plan to ensure that Terraform will create the desired infrastructure:

   ```
   terraform plan
   ```

7. Apply the Terraform configuration to create the Azure infrastructure:

   ```
   terraform apply
   ```

8. After the deployment completes successfully, Terraform will output information about the created resources. You can use this information to access and manage your Azure infrastructure.

9. To tear down the deployed resources and clean up the environment, run:

   ```
   terraform destroy
   ```

## Terraform Configuration

The Terraform configuration in `main.tf` defines the Azure infrastructure components to be provisioned. Here's an overview of the resources created:

- Resource Group: Defines an Azure resource group to contain all deployed resources.
- Virtual Network: Specifies a virtual network (VNet) with associated subnets for hosting Azure resources.
- Subnets: Defines separate subnets within the virtual network for public and private resources.
- Public IP Address: Creates a public IP address for the public-facing virtual machine.
- Network Interfaces: Configures network interfaces for attaching to virtual machines in the public and private subnets.
- Virtual Machines: Deploys virtual machines in both the public and private subnets, running Ubuntu Server.
- Network Security Groups (NSGs): Defines NSG rules to control inbound and outbound traffic for the public and private subnets.

## Additional Resources

- Terraform Documentation: https://www.terraform.io/docs/index.html
- Azure Provider Documentation: https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs

