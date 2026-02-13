# terraform-azure-resourcegroup

Terraform Azure Resource Group Module
This Terraform module provides a standardized way to deploy and manage Azure Resource Groups. Resource groups are logical containers for resources deployed on Azure, and using this module ensures consistent naming conventions and tagging across your infrastructure.

## Features

Standardization: Ensures consistent naming and location settings.

Tagging: Supports a map of tags for cost tracking and management.

Simplicity: Minimal configuration required to get up and running.

## Usage
Add the following block to your Terraform configuration:

 ``` Terraform
module "resource_group" {
source  = "adityatetali/resourcegroup/azurerm" # Update this if using a different source
  version = "1.0.0"

  name     = "rg-project-prod-001"
  location = "East US"

  tags = {
    Environment = "Production"
    Department  = "IT"
    ManagedBy   = "Terraform"
  }
}
```

## Inputs
NameDescriptionTypeDefaultRequirednameThe name of the resource group.stringn/aYeslocationThe Azure Region where the resource group should exist.stringn/aYestagsA mapping of tags to assign to the resource.map(string){}NoOutputsNameDescriptionidThe ID of the Resource Group.nameThe name of the Resource Group.locationThe location of the Resource Group.RequirementsNameVersionterraform>= 1.0.0azurerm>= 3.0.0

OutputsNameDescriptionidThe ID of the Resource Group.nameThe name of the Resource Group.locationThe location of the Resource Group.
