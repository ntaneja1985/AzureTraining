## Azure Solutions Architect

- ![alt text](image.png)
- ![alt text](image-1.png)
- ![alt text](image-2.png)
- ![alt text](image-3.png)
- ![alt text](image-4.png)
- ![alt text](image-5.png)
- ![alt text](image-8.png)

## Types of Cloud Services 
- ![alt text](image-9.png)
- ![alt text](image-10.png)
- ![alt text](image-11.png)
- ![alt text](image-12.png)
- ![alt text](image-13.png)
- ![alt text](image-14.png)
- ![alt text](image-15.png)
- ![alt text](image-16.png)
- ![alt text](image-17.png)

## Types of Clouds 
- ![alt text](image-18.png)
- ![alt text](image-19.png)
- ![alt text](image-20.png)
- ![alt text](image-21.png)
- ![alt text](image-22.png)
- ![alt text](image-24.png)
- ![alt text](image-25.png)

## Introduction to Azure 
- ![alt text](image-26.png)
- ![alt text](image-27.png)
- ![alt text](image-28.png)
- ![alt text](image-29.png)
- ![alt text](image-30.png)
- ![alt text](image-31.png)
- ![alt text](image-32.png)

## Azure Services 
- ![alt text](image-33.png)

## Azure Portal 
- Tenant: It is basically the user directory that Azure is using. 
- ![alt text](image-34.png)
- Integrating an existing Active Directory (AD) with Azure Active Directory (Azure AD) can be a great way to streamline your organization's identity management and provide seamless access to cloud services
- Install Azure AD Connect: This tool from Microsoft simplifies the synchronization of on-premises AD with Azure AD
- Configure Azure AD Connect: During the setup, you'll need to configure the synchronization settings, such as selecting the directories to sync and setting up the sync schedule
- Synchronize User Accounts: Once Azure AD Connect is configured, it will start synchronizing user accounts from your on-premises AD to Azure AD
- Verify Synchronization: Check the synchronization status and ensure that user accounts are being correctly synced to Azure AD
- Set Up Conditional Access and Multi-Factor Authentication (MFA): Implement security measures like conditional access policies and MFA to enhance the security of your integrated environment

## Difference between Subscription and Account 
- ![alt text](image-35.png)

## Resource Groups
- It is a logic container that holds related resources for an Azure solution. 
- Used for grouping resources by a logic boundary.
- We can have resource groups for Development, Test and Production.
- We can also have separate resource groups by teams.
- The resource group can include all the resources for the solution, or only those resources that you want to manage as a group. 
- You decide how you want to allocate resources to resource groups based on what makes the most sense for your organization
- We can create a resource group with the following command:
```shell 
# In Bash use this command
 az group create -l eastus -n CLITest-rg

 # In powershell use this command
 New-AzResourceGroup -Name Test-rg -Location eastus

 # Delete Resource Group like this 
 Remove-ResourceGroup -Name Test-rg
```

## Basic Azure Concepts 
- ![alt text](image-36.png)
- Regions should be selected based on geographical proximity to the target audience. 
- Not every Azure Service is available in every region. 
- Every region has an availability zone. If data center fails, it can go into the availability zone. 
- Pricing also differs by region. 
### Difference between resource groups and subscriptions 
- Cost is always per subscription. 
- Subscriptions are account level(cost-center) containers. 
- Resource Groups are the actual containers for resources. 
- We also have management groups which are used to manage subscriptions. 
- ![alt text](image-38.png)
- It is a good practice to have an "rg" or "RG" as part of resource group name. 
- Almost every resource is placed inside a resource group. 
### Storage Account 
- Used to store almost anything in Azure. 
- Used transparently by various services.
- It can be used to store database backups or VM disks. 
- Also used for explicit data storage. 
- It is quite cheap. 

### SLA 
- Service Level Agreement. 
- ![alt text](image-39.png)
- ![alt text](image-40.png)
- Free Tiers or Shared Tiers offer no SLA. 
- Premium Tiers offer high SLA. 
- ![alt text](image-41.png)

### Cost 
- Everything in Cloud costs money 
- ![alt text](image-42.png)
- In reservations we pay upfront for like 3 years and get a big discount. 
- Always check resource's cost before provisioning. 
- Check for more cost-effective alternatives. 
- Look for reservations when available and relevant. 
- Use Azure's pricing calculator. 
- We can also create Budgets like this 
- ![alt text](image-43.png)

## Architects and the Cloud 
- ![alt text](image-44.png)
- ![alt text](image-45.png)

## Introduction to the App 
- We will create a bookshop on the cloud. 
- It contains 4 main services: Books Catalog, Shopping Cart, Inventory Management and Order Engine. 
- Will be developed using .NET Core and Node.JS 


## Azure Compute