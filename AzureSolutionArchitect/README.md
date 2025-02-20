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
- Set of Cloud Services for hosting and running applications
- Upload code and run it
- Offers various levels of control and flexibility.
- 4 main types of compute services
- Virtual Machines
- App Services
- AKS 
- Azure Functions 

### Virtual Machines 
- A virtual server running on a physical server.
- Allows creating new servers extremely quickly. 
- Based on existing resources of the physical server. 
- Also called an unmanaged service. We manage everything on the VM. 
- Class IaaS service. 
- Hypervisor manages virtual machines on physical server. 
- ![alt text](image-46.png)
- In Azure it works as follows:
- ![alt text](image-47.png)
- ![alt text](image-48.png)
- Always check the price! It varies a lot.
- Use the pricing calculator to calculate price of VM. 
- Prices vary per region. 
- ![alt text](image-49.png)
- ![alt text](image-50.png)
- Every virtual machine in Azure is connected to a virtual network 
- NSG is like a mini-firewall which determines who can access our VM. 
- Every VM must come with a disk 
- ![alt text](image-51.png)
- VM also have a public IP Address with a VM
- ![alt text](image-52.png)
- Image of the Virtual Machine is stored in a stored account and we need to pay for this storage.
- ![alt text](image-54.png)
- ![alt text](image-55.png)
- Auto Shutdown shuts down the machine when not needed, but storage and IP costs are still incurred.
- This can save > 50% of the VM cost. 
- ![alt text](image-56.png)
- Reserved instances allow upfront payment with substantial discount. 
- They are offered for 1-3 years. 
- Great for Production machines which run continuously. 
- Spot instances run on unused capacity in Azure. 
- However these machines can be evicted any moment when needed by Azure. 
- These spot instances offer upto 90% discount, price fluctuates according to demand.
- Great for non-critical, non-continuous tasks 
- Good for batch processes, long running instances. 
- ![alt text](image-58.png)
- For disk optimization select the right disc for the machine.
- Default is Premium SSD. 
- Disk Type affects the SLA. 
- ![alt text](image-59.png)

## Availability of a VM 
- How to distribute VM instances across Azure. 
- ![alt text](image-60.png)
- ![alt text](image-61.png)
- Fault Domain: Logical group of physical hardware that share a common power source and network switch. 
- Similar to rack in a traditional data center. 
- ![alt text](image-63.png)
- A rack is a fault domain. 
- Update domain: Logical group of physical hardware that can undergo maintenance and be rebooted at the same time. 
- Maintenance is done by Azure at its own discretion. 
- ![alt text](image-64.png)
- Fault Domain is physical hardware, it is a rack, update domain is a logical definition. 
- Host machines in update domain can be spread across multiple fault domains.  
- Availability Set: It is a collection of Fault Domains and Update Domains, our VMs will be spread across. 
- Can contain upto 3 fault domains and upto 20 update domains. 
- All domains(Fault and Update) are in the same Zone (=datacenter) 
- ![alt text](image-65.png)
- ![alt text](image-67.png)
- Without availability set, both the VMs could have been placed on the same fault domain. If the fault domain is down, then both VMs are down. 
- ![alt text](image-68.png)
- Availability Zone is a physically separate zone within an Azure region. 
- It is basically a building containing an autonomous data center. 
- Each zone functions as a fault and update domain. 
- Availability Zone provides protection against complete zone shutdown, hence better SLA. 
- ![alt text](image-69.png)
- Availability Zone is also free, we only pay for the additional VMs. 
- ![alt text](image-70.png)
- In a VM we have option of Locally Redundant Storage or Zone Redundant Storage(LRS or ZRS)


## ARM Templates 
- ARM template is a declarative way of deploying resources. 
- ![alt text](image-72.png)
- It is a JSON file describing the resource(s) to be created.
- Used by Azure in all deployments. 
- Good thing is that it can exported, modified and deployed or created from scratch. 
- ![alt text](image-73.png)
- The ARM template has 3 parts: Parameters, Variables and Resources. 
- When we download an ARM template, we get 2 files: template.json and parameters.json 
- ![alt text](image-74.png)
- ![alt text](image-75.png)
- ![alt text](image-76.png)
- ![alt text](image-77.png)
- Inside the parameters.json we can change parameters like we can change osDiskType from "Premium_LRS" to "StandardSSD_LRS"
- Once we change parameters.json file, we can go to the Cloud Shell, go to Manage Files and upload the parameters.json and template.json files. 
- Then inside the cloud shell, we can execute this command: 
```shell 
 az deployment group create --resource-group resource_group_name --template-file template.json --parameters parameters.json
```
- This will deploy our ARM template and corresponding resources will be created. 

## Virtual Machine Scale Sets 
- Group of separate VMs sharing the same image
- Managed as a group 
- Can be scaled out or in manually or according to predefined conditions 
- Great for handling unpredictable load. 
- However, once it is setup machines should not be modified. 
- New machines created by scale set will be based on original image.
- We should create a new image and modify the base image. 
- For webapps, a load balancer should be placed in front of scale set, because the client calls a particular IP Address. 
- Remember, each VM created by scale set will have a different IP Address. 
- ![alt text](image-78.png)
- Scale set is free, but we pay for the VMs deployed inside of it.  
- ![alt text](image-79.png)
- ![alt text](image-80.png)
- We can specify conditions to specify how to scale out and scale in  
- ![alt text](image-81.png)
- ![alt text](image-82.png)
- ![alt text](image-83.png)
- ![alt text](image-85.png)
- ![alt text](image-86.png)
- ![alt text](image-87.png)


## Azure Instance Metadata Services 
- Not a much known feature of Azure VMs 
- It is a REST API accessible from the VM 
- Provides information about VM such as SKU, storage, networking, scheduled events 
- This API is accessible only from the VM not from the outside world. 
- What happens is that if the VM is part of a scaleset, it gets notification about an upcoming eviction. 
- If there is any final actions we need to run, we can do it before eviction. 
- Can be polled every ~1 minute to get enough time to clean things up.  
- To verify this, inside the VM, download POSTMAN tool.
- ![alt text](image-88.png)
```shell 

# Links to access the Instance Metadata endpoints
 IMDS Links
==========
http://169.254.169.254/metadata/instance?api-version=2021-12-13

http://169.254.169.254/metadata/scheduledevents?api-version=2020-07-01

```
- ![alt text](image-89.png)
- We can query the scheduled events endpoint to get the list of upcoming events like this 
- ![alt text](image-90.png)

## Installing the app over VM 
- First we publish our code using dotnet publish command
- Next, we can provision a VM, install IIS on it.
- ![alt text](image-91.png)
- We also need to install hosting bundle of .NET 8 to run .NET 8 apps. 
- Hosting Bundle knows how to integrate into IIS, other ASP.NET runtimes are meant to run as standalone apps. 
- Copy our published folder into the VM folder. 
- Next we need to configure IIS to run the .NET 8 webapp.  
- Create a new website in IIS. 
- Specify the Sitename and physical path. 
- ![alt text](image-92.png)
- Azure by default blocks access to VMs, so we cannot access the website from outside. 
- We can define DNS name for the VM, so that it will be accessible not just using its IP. This can be done by clicking the DNS Name: Configure link in the Overview page.

## Azure Architecture Icons 
- We can download the architecture icons from here:
- https://learn.microsoft.com/en-us/azure/architecture/icons/


## Azure App Services
- Fully managed web hosting for websites.
- Publish the code and it just runs. 
- Here we have no access to underlying servers.
- Always secure and compliant of the underlying infrastructure.
- Integrates well with many source controls and DevOps engines like Github Actions, Azure Devops, Bitbucket. 
- Supports .NET, .NET Core, Node.JS, Java, Python, PHP. 
- Also supports containers. Upload the container and it runs. 
- Supports WebAPIs, WebApps, WebJobs(batch processes)
- Very easy to deploy. 
- ![alt text](image-93.png)
- ![alt text](image-94.png)
- Standard or Premium App Service Tiers is the best for most cases. 
- App Services can be autoscaled to support spikes in load. 
- Autoscale is based on various metrics.
- ![alt text](image-95.png)
- We can create scale conditions. 
- ![alt text](image-96.png)
- Standard plan offers autoscaling and Deployment Slots. 
- In App Service Editor we can see the files uploaded to App Service
- ![alt text](image-97.png)
- In the App Service console, we can have command line access to the VM running our code. 
- ![alt text](image-98.png)
- In the App Service plan we can see metrics about the underlying VM 
- ![alt text](image-99.png)
- In Scale out, we can choose how to scale out the app-service. 
- ![alt text](image-100.png)
- We can manually set the app service instance counts or we can setup rule based auto-scaling. 
- We can select Custom autoscale. 
- ![alt text](image-101.png)
- App Services have multiple outbound IP Addresses. 
- ![alt text](image-102.png)
- By default, App Services can be accessed using http and https. You can make it https only in the TLS/SSL settings in the App Service menu.
- App service can run also batch processes, or continuous jobs, and not only web apps with the request / response  paradigm. This can be done using the WebJobs menu item, where you can upload exe file that will run always, or on scheduled times.
- Want to know the IP address of the App Service? Take a look at the Properties of the page. You can find there the Virtual IP address of the App Service, and also - the Outbound IP addresses. Note the plural - App Service can have more than one outbound IP address.
- Want to know how much storage did you use, and what are the current usage statistics? Go to Quotas for this data.

## App Service Deployment Slots. 
- When we upload the code to app service, new version is available immediately.
- Sometimes, we want to test the version before publishing it. 
- Deployment slots allow us to upload code and test it separately from the main site.
- After validation, we swap the slots and promote it to production. 
- New slots are created from the portal 
- Number of allowed slots depends on the plan. Standard plans allow for upto 5 slots. 
- Slot is a fully functional app service with a dedicated URL. 
- Slots are free and do not incur additional costs. 
- Traffic can be split between slots. 
- Some users will be routed to production and some to the new slot. 
- Great to get feedback from the end users. 
- ![alt text](image-103.png)
- ![alt text](image-104.png)
- ![alt text](image-105.png)
- We can also swap slots
- ![alt text](image-106.png)
- ![alt text](image-107.png)

## Deployment Types 
- ![alt text](image-108.png)
- ![alt text](image-109.png)
- ![alt text](image-110.png)
- ![alt text](image-111.png)
- ![alt text](image-112.png)
- ![alt text](image-113.png)
- ![alt text](image-114.png)
- ![alt text](image-115.png)
- ![alt text](image-116.png)
- ![alt text](image-117.png)

## Azure Kubernetes Service (AKS)
- Managed K8s on Azure
- Allows deploying containers and managing them using K8s 
- No payment for AKS itself, we pay only for instances used by AKS(VMs)
- Containers package software, dependencies and configuration files and can be copied between machines. 
- Containers use the underlying OS. 
- ![alt text](image-118.png)
- ![alt text](image-119.png)
- ![alt text](image-120.png)
- ![alt text](image-124.png)
- ![alt text](image-125.png)
- ![alt text](image-126.png)
- ![alt text](image-127.png)
- ![alt text](image-128.png)
- We face problems of deployment, scalability, monitoring, routing and high availability in lot of containers. 
- With VMs we solve this problem with VM Scale Sets and load balancers, but how to do in Containers. Enter Kubernetes. 
- K8s is the defacto standard for container management 
- Provides routing, scaling, configuration management etc. 
- In k8S we have pods. A pod is a container of containers. 
- Pods expose an IP Address
- We have services in K8s such as NodePort, ClusterIP, LoadBalancer to expose the pod to the outside world. 
- ![alt text](image-129.png)
- Command to build a docker image using Azure CLI :
```shell 
az acr build --image cart:v1 --registry <REGISTRY NAME> --file Dockerfile .

```
- ![alt text](image-130.png)

## Using Azure Container Registry 
- Use the following commands 
```shell 
# login to azure 
az login 

# login to container registry 
ax acr login --name readitnishantacr 

# Build the docker image 
docker build -t readitnishantacr.azurecr.io/cart:v1 .

# Push the docker image to ACR 
docker push readitnishantacr.azurecr.io/cart:v1


```
- ![alt text](image-131.png)

## Managing Image using AKS 
- ![alt text](image-132.png)
- ![alt text](image-133.png)
- ![alt text](image-134.png)
- Run the following commands to run our cart project inside AKS 
- First download and install K8s CLI
```shell 
# install AKS cli 
az aks install-cli

# Login to azure
az login 

# Connect to the AKS cluster we create in azure 
az aks get-credentials --resource-group readit-app-rg --name cart-aks

# Get the nodes using kubectl command 
kubectl get nodes 

# apply the deployment.yaml file
kubectl apply -f deployment.yaml

```
- Here is the sample deployment.yaml file used by K8s 
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: readit-cart
spec:
  selector:
    matchLabels:
      app: readit-cart
  template:
    metadata:
      labels:
        app: readit-cart
    spec:
      containers:
      - name: readit-cart
        image: readitnishantacr.azurecr.io/cart:v1
        resources:
          limits:
            memory: "128Mi"
            cpu: "500m"
        ports:
         - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
  name: readit-cart
spec:
  type: LoadBalancer
  ports:
  - port: 80
    targetPort: 5004
  selector:
    app: readit-cart      

```

- ![alt text](image-135.png)
- ![alt text](image-136.png)
- Click on the External IP and the application will run fine. 
- ![alt text](image-137.png)


## Azure Functions
- Small focused functions running as a result of an event. 
- Great for Event Driven systems
- Automatically managed by Azure(Start, Stop, Autoscale)
- Serverless (Cloud resource completed managed by cloud, no need to bother about VM, CPU, Memory etc)
- Flexible Pricing Plans 
- They just work. 
- But still runs on actual servers. 
- ![alt text](image-138.png)
- The above is an HttpTrigger function(Triggered as result of HTTP call and its authorization level is anonymous) that creates a new EventGrid Event by extracting the name property from the incoming request.
- Result of this function is written into an event grid.
- ![alt text](image-140.png)
- ![alt text](image-141.png)
- ![alt text](image-142.png)
- ![alt text](image-143.png)
- ![alt text](image-144.png)
- We can create an Azure function without trigger also. 
- Supported languages for Azure Functions is C#, Javascript(NodeJS), Java, Python, Powershell, F#
- Bindings help us to create connection between Azure function and other resources in the cloud (such as Service Bus, Event Grid)
- Bindings are provided as parameter to the function. 
- ![alt text](image-139.png)
### Azure functions have problem of ColdStart. 
- This is a problem mostly faced by Http Trigger functions. 
- ![alt text](image-146.png)
- ![alt text](image-147.png)
- We can avoid cold starts by selecting the right hosting plan 

## Azure Function Hosting Plans 
- ![alt text](image-148.png)
- In Consumption Plan we pay for what we use. 
- ![alt text](image-149.png)
- In consumption plan there is limit of 1.5GB RAM. 
- ![alt text](image-150.png)
- Downsides of Consumption plan are 1.5 GB RAM limit and cold starts. 
- In premium plan we pay for pre-warmed instances(hosts)
- ![alt text](image-152.png)
- In premium plan we dont have cold starts, also there is no memory limit(up to host RAM) and we have better performance and we get VNET configuration and we also get predictable price. 
- ![alt text](image-153.png)
- Downsides of Premium plan is that it is more expensive.
- Finally we have dedicated plan. 
- Here functions run on an existing App Service. 
- This is great if server hosting app service is under-utilized. 
- There are no additional costs for the dedicated plan . 
- In settings of App Service, make sure Always ON setting is activated to avoid disabling functions
- ![alt text](image-154.png)
- In Dedicated Plan, there is no auto-scale support. 

## Durable Functions 
- Stateful functions that interact with external resources and keep track of flow. 
- Offer simple syntax, hide complexities of managing state, retries etc. 
- Useful for Function Chaining(call various functions sequentially and apply output of each fn to the next one)
- ![alt text](image-155.png)
- ![alt text](image-156.png)


- Client Function: : Starts the orchestration.
```c#
// Example of client function
 [FunctionName("StartFunction")]
public static async Task<IActionResult> Start(
    [HttpTrigger(AuthorizationLevel.Function, "get", "post")] HttpRequest req,
    [DurableClient] IDurableOrchestrationClient starter,
    ILogger log)
{
    string instanceId = await starter.StartNewAsync("ChainingOrchestrator", null);
    log.LogInformation($"Started orchestration with ID = '{instanceId}'.");
    return starter.CreateCheckStatusResponse(req, instanceId);
}


```
- Orchestrator Function: Defines the workflow using durable tasks.
```c#
//Defines the workflow
 [FunctionName("ChainingOrchestrator")]
public static async Task<List<string>> RunOrchestrator(
    [OrchestrationTrigger] IDurableOrchestrationContext context)
{
    var results = new List<string>();

    results.Add(await context.CallActivityAsync<string>("HelloFunction", "Tokyo"));
    results.Add(await context.CallActivityAsync<string>("HelloFunction", "Seattle"));
    results.Add(await context.CallActivityAsync<string>("HelloFunction", "London"));

    return results;
}


```
- Activity Function: Performs the actual work. Called by the orchestrator function.
```c#
//Performs the actual work
 [FunctionName("HelloFunction")]
public static string SayHello([ActivityTrigger] string name, ILogger log)
{
    log.LogInformation($"Saying hello to {name}.");
    return $"Hello, {name}!";
}


```
- State Management: Automatically manages state, making it easier to write stateful applications.

- Reliable: Durable Functions ensures reliability with automatic retries.

- Scalable: Can scale out based on the demand and workload.

### Storing State in Durable functions
- Durable Functions store state in Azure Storage Tables by default. 
- Each function app configured to use Durable Functions has its state managed through three main types of Azure Storage tables:
- Instances Table: Stores the state, metadata, and history of each orchestration instance.
- History Table: Keeps the detailed execution history of each orchestration, including input/output data, execution status, and timestamps.
- Auxiliary Table: Used for managing additional data and intermediate state required by the runtime.
### Statuses returned by Durable Functions
- Durable Functions can return several statuses that indicate the current state of an orchestration instance. Here are the primary statuses:
- Running: The orchestration is currently in progress.
- Completed: The orchestration has finished successfully.
- ContinuedAsNew: The orchestration has restarted itself with new input.
- Failed: The orchestration has encountered an error and has stopped executing.
- Canceled: The orchestration has been canceled by a client request.
- Terminated: The orchestration has been forcibly terminated by a client request.
- Pending: The orchestration has not yet started.

### host.json file
- The host.json file in Azure Functions is used to configure various global settings and behaviors for the function app. It's essentially a configuration file for the function host runtime. Here are some of the key areas you can configure with host.json:
- Version: Specifies the version of the host configuration schema.
- Function Timeout: Defines the maximum execution duration for a function.
- Logging: Configures logging settings, such as log level and categories.
- Bindings: Configures binding settings for specific triggers like HTTP, timers, queues, and more.
- Retry Policies: Sets retry policies for failed executions.
- Extensions: Configures settings for various extensions, like Durable Functions.
- Example is as follows:
```json 
 {
  "version": "2.0",
  "extensions": {
    "durableTask": {
      "hubName": "MyTaskHub"
    }
  },
  "logging": {
    "logLevel": {
      "Function": "Information"
    }
  },
  "functionTimeout": "00:10:00",
  "queues": {
    "maxDequeueCount": 5,
    "visibilityTimeout": "00:00:30"
  },
  "healthMonitor": {
    "enabled": true,
    "healthCheckInterval": "00:05:00"
  }
}


```

## Running Azure Functions locally
- We must have the Azure Functions Core Tools installed. 
- ![alt text](image-157.png)
- ![alt text](image-158.png)

## Running Azure Functions with various Triggers and updating Azure Sql Server Database
- Consider the following scenarios 
- We need a function to run when a blob is uploaded, to resize the blob and update its status in the database. 
- In this case consider the following local.settings.json file 
- Use local.settings.json for local development only. Do not deploy this file to production.
```json
{
    "IsEncrypted": false,
  "Values": {
    "AzureWebJobsStorage": "DefaultEndpointsProtocol=https;AccountName=azuredotnetmastery;AccountKey=dEnt4cnUh3nHyfPhL7F3Bw+ZAbpN7g34r5YPxI+BOFqscvcLSsGh+CckIBkMr3fqd/KmoNz/vCDaHqIyqdl77w==;EndpointSuffix=core.windows.net",
    "FUNCTIONS_WORKER_RUNTIME": "dotnet",
    //"AzureSqlDatabase": "Server=tcp:dotnetmasterysqlserver.database.windows.net,1433;Initial Catalog=dotnetmastery-azureSQL;Persist Security Info=False;User ID=admin-sql;Password=DotnetMastery1;MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=False;Connection Timeout=30;",
    "AzureSqlDatabase": "Server=(localdb)\\mssqllocaldb;Database=AzureDotNetMasterySQL;Trusted_Connection=True;MultipleActiveResultSets=true",
    "CustomSendGridKeyAppSettingName": "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"
  }
}

```
- Also consider the following Startup.cs file to setup the DbContext for the Azure SQL Server Database
```c#
﻿using AzureTangyFunc;
using AzureTangyFunc.Data;
using Microsoft.Azure.WebJobs;
using Microsoft.Azure.WebJobs.Hosting;
using Microsoft.EntityFrameworkCore;
using Microsoft.Extensions.DependencyInjection;


[assembly: WebJobsStartup(typeof(Startup))]
namespace AzureTangyFunc
{
    public class Startup : IWebJobsStartup
    {
        public void Configure(IWebJobsBuilder builder)
        {
            string connectionString = Environment.GetEnvironmentVariable("AzureSqlDatabase");

            builder.Services.AddDbContext<AzureTangyDbContext>(
                options => options.UseSqlServer(connectionString));

            builder.Services.BuildServiceProvider();
        }
    }
}

```
- We need to include the following references in the Azure Functions project 
```c#
 <PackageReference Include="Microsoft.Azure.WebJobs.Extensions.SendGrid" Version="3.0.2" />
    <PackageReference Include="Microsoft.Azure.WebJobs.Extensions.Storage" Version="5.0.0-beta.5" />
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="6.0.0-rc.1.21452.10" />
    <PackageReference Include="Microsoft.EntityFrameworkCore.SqlServer" Version="6.0.0-rc.1.21452.10" />
    <PackageReference Include="Microsoft.NET.Sdk.Functions" Version="4.0.0-preview2" />
    <PackageReference Include="SixLabors.ImageSharp" Version="1.0.4" />

```
- Then we define the Azure Function to run with Blob Trigger as follows to update the status in the database:
```c#
 namespace AzureTangyFunc
{
    public class BlobResizeTriggerUpdateStatusInDb
    {
        private readonly AzureTangyDbContext _db;
        public BlobResizeTriggerUpdateStatusInDb(AzureTangyDbContext db)
        {
            _db = db;
        }

        [FunctionName("BlobResizeTriggerUpdateStatusInDb")]
        public void Run([BlobTrigger("functionsalesrep-sm/{name}", Connection = "AzureWebJobsStorage")]Stream myBlob, 
            string name, ILogger log)
        {
            log.LogInformation($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");

            var fileName = Path.GetFileNameWithoutExtension(name);
            SalesRequest salesRequestFromDb = _db.SalesRequests.FirstOrDefault(u => u.Id == fileName);
            if (salesRequestFromDb != null)
            {
                salesRequestFromDb.Status = "Image Processed";
                _db.SalesRequests.Update(salesRequestFromDb);
                _db.SaveChanges();
            }
        }
    }
}


```

- We can have an azure function to resize an image on Blob Upload as follows: 
```c#
 namespace AzureTangyFunc
{
    public static class ResizeImageOnBlobUpload
    {
        [FunctionName("ResizeImageOnBlobUpload")]
        public static void Run([BlobTrigger("functionsalesrep/{name}", Connection = "AzureWebJobsStorage")]Stream myBlob,
            [Blob("functionsalesrep-sm/{name}", FileAccess.Write)] Stream myBlobOutput,
            string name, ILogger log)
        {
            log.LogInformation($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");

            using Image<Rgba32> input = Image.Load<Rgba32>(myBlob, out IImageFormat format);
            input.Mutate(x => x.Resize(300, 200));
            input.Save(myBlobOutput, format);
        }
    }
}


```
- We can have an Http trigger function that adds an item to the Queue on a POST request
```c#
 namespace AzureTangyFunc
{
    public static class OnSalesUploadWriteToQueue
    {
        [FunctionName("OnSalesUploadWriteToQueue")]
        public static async Task<IActionResult> Run(
            [HttpTrigger(AuthorizationLevel.Function, "get", "post", Route = null)] HttpRequest req,
            [Queue("SalesRequestInBound",Connection ="AzureWebJobsStorage")] IAsyncCollector<SalesRequest> salesRequestQueue,
            ILogger log)
        {
            log.LogInformation("Sales Request received by OnSalesUploadWriteToQueue function");

           

            string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
            SalesRequest data = JsonConvert.DeserializeObject<SalesRequest>(requestBody);

            await salesRequestQueue.AddAsync(data);

            string responseMessage = "Sales Request has been received for ." + data.Name;
            return new OkObjectResult(responseMessage);
        }
    }
}

```
- We can have a Queue trigger function to process a Queue item and add it to the database like this 
```c#
 namespace AzureTangyFunc
{
    public class OnQueueTriggerUpdateDatabase
    {
        private readonly AzureTangyDbContext _db;

        public OnQueueTriggerUpdateDatabase(AzureTangyDbContext db)
        {
            _db = db;
        }


        [FunctionName("OnQueueTriggerUpdateDatabase")]
        public void Run([QueueTrigger("SalesRequestInBound", Connection = "AzureWebJobsStorage")]SalesRequest myQueueItem, 
            ILogger log)
        {
            log.LogInformation($"C# Queue trigger function processed: {myQueueItem}");

            myQueueItem.Status = "Submitted";
            _db.SalesRequests.Add(myQueueItem);
            _db.SaveChanges();


        }
    }
}

```
- We can also have a Timer Trigger Azure Function that at certain intervals checks the Sales Request Table in the Azure Sql Database and sends an email using SendGrid and updates the status in the database

```c#
public  class UpdateStatusToCompletedAndSendEmail
    {
        private readonly AzureTangyDbContext _db;
        public UpdateStatusToCompletedAndSendEmail(AzureTangyDbContext db)
        {
            _db = db;
        }

        [FunctionName("UpdateStatusToCompletedAndSendEmail")]
        public async Task Run([TimerTrigger("0 */5 * * * *")]TimerInfo myTimer,
            [SendGrid(ApiKey = "CustomSendGridKeyAppSettingName")] IAsyncCollector<SendGridMessage> messageCollector, ILogger log)
        {
            log.LogInformation($"C# Timer trigger function executed at: {DateTime.Now}");

            IEnumerable<SalesRequest> salesRequestFromDb = _db.SalesRequests.Where(u => u.Status == "Image Processed");
            foreach (var salesReq in salesRequestFromDb)
            {
                //for each request update status
                salesReq.Status = "Completed";
            }

            _db.UpdateRange(salesRequestFromDb);
            _db.SaveChanges();

            var message = new SendGridMessage();
            message.AddTo("dotnetmastery@gmail.com");
            message.AddContent("text/html", $"Processing completed for {salesRequestFromDb.Count()} records");
            message.SetFrom(new EmailAddress("hello@dotnetmastery.com"));
            message.SetSubject("Azure Tangy Processing Successful");
            await messageCollector.AddAsync(message);
        }
    }

```
- We can also use Azure Functions to host and run a WebAPI as follows:
```c#
 public class GroceryAPI
    {
        private readonly AzureTangyDbContext _db;

        public GroceryAPI(AzureTangyDbContext db)
        {
            _db = db;
        }


        [FunctionName("CreateGrocery")]
        public async Task<IActionResult> CreateGrocery(
            [HttpTrigger(AuthorizationLevel.Function, "post", Route = "GroceryList")] HttpRequest req,
            ILogger log)
        {
            log.LogInformation("Creating Grocery List Item.");

            
            string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
            GroceryItem_Upsert data = JsonConvert.DeserializeObject<GroceryItem_Upsert>(requestBody);

            var groceryItem = new GroceryItem
            {
                Name = data.Name
            };

            _db.GroceryItems.Add(groceryItem);
            _db.SaveChanges();

            return new OkObjectResult(groceryItem);
        }

        [FunctionName("GetGrocery")]
        public async Task<IActionResult> GetGrocery(
           [HttpTrigger(AuthorizationLevel.Function, "get", Route = "GroceryList")] HttpRequest req,
           ILogger log)
        {
            log.LogInformation("Getting all Grocery List Item.");

            return new OkObjectResult(_db.GroceryItems.ToList());
        }

        [FunctionName("GetGroceryById")]
        public async Task<IActionResult> GetGroceryById(
         [HttpTrigger(AuthorizationLevel.Function, "get", Route = "GroceryList/{id}")] HttpRequest req,
         ILogger log, string id)
        {
            log.LogInformation("Getting Grocery List Item by ID.");
            var item = _db.GroceryItems.FirstOrDefault(u => u.Id == id);
            if (item == null)
            {
                return new NotFoundResult();
            }

            return new OkObjectResult(item);
        }


        [FunctionName("UpdateGrocery")]
        public async Task<IActionResult> UpdateGrocery(
           [HttpTrigger(AuthorizationLevel.Function, "put", Route = "GroceryList/{id}")] HttpRequest req,
           ILogger log, string id)
        {
            log.LogInformation("Updatind Grocery List Item.");
            var item = _db.GroceryItems.FirstOrDefault(u => u.Id == id);
            if (item == null)
            {
                return new NotFoundResult();
            }

            string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
            GroceryItem_Upsert updatedData = JsonConvert.DeserializeObject<GroceryItem_Upsert>(requestBody);

            if (!string.IsNullOrEmpty(updatedData.Name))
            {
                item.Name=updatedData.Name;
                _db.GroceryItems.Update(item);
                _db.SaveChanges();
            }

            return new OkObjectResult(item);
        }

        [FunctionName("DeleteGrocery")]
        public async Task<IActionResult> DeleteGrocery(
           [HttpTrigger(AuthorizationLevel.Function, "delete", Route = "GroceryList/{id}")] HttpRequest req,
           ILogger log, string id)
        {
            log.LogInformation("Delete Grocery List Item.");


            var item = _db.GroceryItems.FirstOrDefault(u => u.Id == id);
            if (item == null)
            {
                return new NotFoundResult();
            }
            _db.GroceryItems.Remove(item);
            _db.SaveChanges();

            return new OkResult();
        }
    }

```

## Setting up Security in Azure Functions 
- Setting up security in Azure Functions involves several best practices to ensure your function app is secure. Here are some key steps:
 1. Enable Managed Identity
 Managed identities provide an identity for your function app in Azure Active Directory (AAD), which can be used to access other Azure resources securely.

 2. Use Azure API Management (APIM)
 APIM can be used to authenticate and authorize requests to your function app, providing an additional layer of security.

 3. Deploy to a Virtual Network (VNet)
 Deploying your function app to a VNet allows you to isolate it from the public internet and control network access using Network Security Groups (NSGs).

 4. Enable App Service Authentication/Authorization
 This feature allows you to secure your function app using Azure Active Directory, OAuth 2.0, or other authentication providers.

 5. Use Environment Variables for Secrets
 Store sensitive information like connection strings and API keys in environment variables rather than hardcoding them into your function code.

 6. Enable Application Insights
 Integrate Application Insights to monitor and detect security threats, performance issues, and operational problems.

 7. Implement Role-Based Access Control (RBAC)
 Use RBAC to control who has access to your function app and what they can do with it.

 8. Regularly Update and Patch
 Ensure that your function app and its dependencies are regularly updated to protect against vulnerabilities.
 9. Using Azure Key Vault
   - Using Azure Key Vault in Azure Functions allows you to securely store and manage secrets, such as connection strings and API keys, and access them from your function app.
   - Enable System-Assigned Managed Identity: In the Azure Portal, navigate to your Function App, go to Identity, and enable System-assigned Managed Identity.
   - Assign Roles: Assign the necessary roles to the managed identity to allow it to access the Key Vault. Typically, you would assign the Key Vault Secrets User role.
   - Add Key Vault References: In the Azure Portal, navigate to your Function App, go to Configuration, and add new application settings
   - Use Key Vault References: Use the format @Microsoft.KeyVault(SecretUri=<secret-uri>) to reference secrets stored in the Key Vault
   - We can access secrets inside Function App code like this: 
```c#
   using System;
using System.Net.Http;
using System.Threading.Tasks;

public static class MyFunction
{
    [FunctionName("MyFunction")]
    public static async Task<IActionResult> Run(
        [HttpTrigger(AuthorizationLevel.Function, "get", "post")] HttpRequest req,
        ILogger log)
    {
        log.LogInformation("Accessing secret from Key Vault");

        var secretValue = Environment.GetEnvironmentVariable("MySecret", EnvironmentVariableTarget.Process);
        log.LogInformation($"Secret value: {secretValue}");

        return new OkObjectResult($"Secret value: {secretValue}");
    }
}

```
- Example Configuration in host.json
- Here’s an example of how you might configure some of these security features in your host.json file:
```json

{
  "version": "2.0",
  "extensions": {
    "durableTask": {
      "hubName": "MyTaskHub"
    }
  },
  "logging": {
    "logLevel": {
      "Function": "Information"
    }
  },
  "functionTimeout": "00:10:00",
  "networking": {
    "virtualNetworkName": "MyVNet",
    "subnet": "MySubnet"
  },
  "security": {
    "enableAuthentication": true,
    "authenticationProvider": "AzureActiveDirectory"
  },
  "IsEncrypted": false,
  "Values": {
    "AzureWebJobsStorage": "UseDevelopmentStorage=true",
    "FUNCTIONS_WORKER_RUNTIME": "dotnet",
    "MySecret": "@Microsoft.KeyVault(SecretUri=https://mykeyvault.vault.azure.net/secrets/MySecret/)"
  }
}
```



## How to choose the Compute Type 
- ![alt text](image-159.png)
- More Azure Compute Options are Logic Apps, ACI(Azure Container Instance), App Service Container(Deploy container image to App Service)


## Azure Networking

  