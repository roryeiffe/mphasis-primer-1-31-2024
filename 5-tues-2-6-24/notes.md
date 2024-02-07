## IaC
Infrastructure as Code (IaC) is the process of managing and provisioning computer infrastructure through code, as opposed to manual processes. The code serves as the blueprint for your infrastructure, and it can be versioned, tested, and reused. This allows for more efficient and consistent infrastructure management, and it can be used to automate the deployment of applications and services.

Without IaC, when we want to create a new resource, we need to go through the portal. Some of the downsides of this approach include:
- Having to memorize the steps involved in navigating the portal
- If the portal receives an update, the steps could become obsolete
- Hard to repeat these instructions

If we represent our infrastructure using code, then it is easily reproducible. 

## Terraform
Terraform is an infrastructure as code (IaC) tool developed by HashiCorp. It allows you to define and manage the infrastructure of your applications and systems in a human-readable configuration language called HashiCorp Configuration Language (HCL), similar to JSON. This configuration file serves as your blueprint, describing the resources you want to provision, like virtual machines, databases, networks, and more.

Terraform is a solution that can apply to different types of cloud providers like AWS, GCP, Azure. 

## Azure RM Templates
Azure Resource Manager (ARM) templates are JSON files that define the resources you need to deploy for your solution. The template can be used to deploy the resources consistently and repeatedly, and it can be versioned and shared. ARM templates are used to define the infrastructure and configuration of your Azure resources, and they can be used to automate the deployment of your applications and services.


## Resources
- [Terraform Overview](https://www.terraform.io/intro/index.html)
- [Terraform on Azure Overview](https://learn.microsoft.com/en-us/azure/developer/terraform/overview)
- [IaC and Terraform in 100 seconds](https://www.youtube.com/watch?v=tomUWcQ0P3k)
- [Azure ARM Templates](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/overview)
- [Terraform demo with Azure](https://www.youtube.com/watch?v=OAWBHyNKrzw)
