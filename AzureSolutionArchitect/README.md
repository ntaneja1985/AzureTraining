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
- Deals with resource's network connections, firewalls etc. 
- Foundation of Cloud Security. 
- ![alt text](image-160.png)

## Virtual Networks(VNets)
- A network in which we can deploy our cloud resources
- Many cloud resources are deployed within VNets
- Examples are VMs, AppServices, DBs etc. 
- Virtual is based on a physical network, but is logically separated from other virtual networks. 
- Resources in a single VNet can communicate with each other by default, but cannot communicate with other resources in other VNets. 
- ![alt text](image-161.png)
- Think of it as our organizations are their private network. 
- In AWS, it is called Virtual Private Cloud(VPC)
- VNets are free, but there is a limit of 50 VNets per subscription across all regions. 
- VNet is scoped to a single region. 
- VNet cannot span multiple regions. 
- VNet is scoped to a single subscription
- Different VNets can be connected by something through Peering.
- VNets are segmented using Subnets 
- VNets are protected using NSG(on the subnets)
- NSG is defined on the subnet not on the VNet. 
- ![alt text](image-162.png)
- Each VNet has its own address range or IP Range
- Spans 65,536 addresses. 
- All network devices must be in this address range. 
- It is expressed using CIDR notation. 

## CIDR Notation 
- Classless Inter-Domain Routing. 
- It is a method for representing an IP Range. 
- Composed of an address in the range and a number between 0 and 32 
- The number indicates the number of bits that are allocated to the address.
- Smaller the number-larger the range. 
- ![alt text](image-163.png)
- ![alt text](image-164.png)
- For 20 bits
- ![alt text](image-165.png)
- Lot of CIDR calculators.
- ![alt text](image-166.png)

## Subnets
- Logical segment in the VNet
- Shares a subset of the VNet's IP Range. 
- Used as a logical group of resources in the Vnet. 
- Is a must. Resources must be placed in a subnet, cannot be placed directly in the Vnet. 
- Resources in a subnet can talk to resources to resources in other subnets in the same VNet. 
- However, this can be customized. 
- ![alt text](image-167.png)
- Each subnet gets a share of the parent Vnet's IP Range.
- NEVER use the full range of the Vnet in a subnet. 
- Once we pick the address range of the subnet, it is very hard to modify it later. Also makes it hard to add future subnets. 
- Subnets are free 
- Limit of 3000 subnets per Vnet. 
- ![alt text](image-169.png)
- ![alt text](image-170.png)
- ![alt text](image-171.png)
- ![alt text](image-172.png)
- ![alt text](image-173.png)
- Here Network Interface is the Virtual Network Card. 
### Unless peering is done, devices placed in different VNets cannot communicate with each other

### what is the advantage of placing the webapp and backend service and database in different vnets
- Placing the web app, backend service, and database in different Virtual Networks (VNets) in Azure, connected via VNet peering, offers several advantages from a security, organization, scalability, and management perspective.
- **Network Segmentation**: By isolating the web app, backend service, and database into separate VNets, you reduce the attack surface. If one layer (e.g., the web app) is compromised, the attacker doesn’t automatically gain access to the backend or database.
- **Granular Access Control**: You can apply Network Security Groups (NSGs) and firewall rules specific to each VNet. For example:
The web app VNet might allow inbound traffic from the internet on port 80/443.
The backend VNet might only allow traffic from the web app VNet.
The database VNet might only permit traffic from the backend VNet on specific ports (e.g., 1433 for SQL).
- **Defense in Depth**: Separating tiers into VNets aligns with a layered security approach, making it harder for threats to propagate.
- Delegation: In large organizations, different teams (e.g., frontend devs, backend devs, DBAs) can manage their own VNets, reducing dependencies and conflicts.
- Independent Scaling: Each VNet can scale independently. For example:
- The web app VNet might need more subnets for load-balanced VMs or App Services.
- The database VNet might need a larger address space for replicas or clusters.
- **Controlled Communication**: With VNet peering, you can fine-tune how traffic flows between tiers. For instance, you can disable forwarded traffic or restrict Gateway Transit to ensure the database VNet isn’t exposed to external networks unnecessarily.
- **Reduced Congestion**: By isolating traffic within each VNet, you minimize the risk of one tier’s network load (e.g., a web app under DDoS attack) impacting the others.
- **Regulatory Compliance**: Many industries (e.g., finance, healthcare) require strict separation of data and application layers. Placing the database in its own VNet helps meet these requirements by isolating sensitive data.
- Fault Isolation: If one VNet experiences an issue (e.g., misconfiguration or outage), the others can remain operational. For example, a web app VNet failure doesn’t necessarily bring down the database.
- A **DDoS attack on the web app** doesn’t directly affect the backend or database due to NSG rules and VNet isolation.


## Network Security Group(NSG)
- Gatekeeper for Subnets
- Defines who can connect in and out of Subnet
- Think of it as mini-firewall 
- Standard part of subnet creation. 
- Is Free of cost
- It works by looking at 5 tuples:
- Source(Where the connection came from), Source Port(The port the source is using), Destination(Where does the connection request go), Destination Port(To which port it wants to connect), Protocol(Whether it uses TCP, UDP or both)
- Based on these 5 tuples, connection is either allowed or denied. 
- This is called Security Rule. 
- Each rule is assigned a number
- Lower the number, higher the priority of the rule. 
- NSG is automatically created and attached to every newly created VM's network interface.
- NSG of a VM automatically opens RDP(on windows) or SSH(on Linux) port to anyone.
- It must be handled first thing after creation. 
- We dont want to leave RDP or SSH ports open to the world. 
- ![alt text](image-174.png)
- In NSG we have inbound port rules and outbound port rules. 
- Note that higher the number of priority, lower is the priority of the rule. 
- Also note the only rule with priority of 300 means that RDP connection can be made using TCP protocol over port 3389. Since it is the lowest number of priority, it has the highest priority.
- ![alt text](image-175.png)
- ![alt text](image-176.png)
- We can make our RDP connection more secure by finding out our IP address and allowing the source to be IP Address and specifying our IP in the Source IP Address field so that only we can connect to the VM from our IP only. 
- ![alt text](image-177.png)
- To allow traffic over port 8080, we need to open that port using the NSG. 
- Remember our app is deployed over port 8080, so now we should be able to access the application running on port 8080.
- ![alt text](image-178.png)
### Please note NSG rules affect external access only, within the private subnet, the devices should still be able to connect with each other. Only traffic from outside world is filtered. Traffic between the subnet is still allowed. 
- To change the subnet for a particular VM, go to the network interface for the VM and select the new subnet. This will restart the VM to use the new subnet.
- ![alt text](image-179.png)
- Note the private IP Address of the VM is now changed. 
- Different resources in different subnets but within the same VNet can still communicate with each other. 
- We can attach the NSG either to a subnet or a VM
- ![alt text](image-180.png)

## Network Peering
- Sometimes, to increase security, we want to place some resources in a completely different Vnet not just Subnet. 
- Examples are separate systems, separate layers like FrontEnd in one Vnet, backend in a different Vnet and Database in a different Vnet. 
- Basically, we dont want to place non-public resources in a Vnet that has public access. 
- ![alt text](image-181.png)
- Place sensitive resources in different Vnets. 
- ![alt text](image-182.png)
- ![alt text](image-183.png)
- To solve the problem of communication between 2 different Vnets, we have network peering.
- It allows 2 Vnets to connect to each other
- From the user's point of view, it is single Vnet. 
- Just make sure address spaces are not overlapped. 
- Use NSG for protection. 
- Peering can work across regions. 
- Remember, Vnet is limited to a single region
- Using Peering, we can make a Vnet that spans across several regions 
- Peering is NOT FREE!
- ![alt text](image-184.png)
- ![alt text](image-185.png)
- While deleting a VM, we can choose not to delete the OS Disk so that we can move that disk across Vnets when recreating the VM with the same disk across a different Vnet. 
- ![alt text](image-186.png)
- In the above if we try to access the weather API in a different Vnet from an application in a different Vnet, it will give the above connection timed out error, as without network peering, we cannot connect across Vnets. 
- To setup network peering, we need to go our Vnet and select Peerings. 
- ![alt text](image-187.png)
- ![alt text](image-189.png)
- ![alt text](image-190.png)
- We already have a rule in NSG that for a peered Vnet, we can connect to this VM.
- But this is not a best practice.
- We add another inbound rule that any other custom service cannot connect to port 8080. 
- ![alt text](image-191.png)
- We will get the private IP Address of catalog VM and then add a new inbound rule in the weather VM NSG, that will allow only this private IP Address to access this weather VM.
- ![alt text](image-192.png)


## Network Topology
- We have something called Network Watcher. 
- ![alt text](image-193.png)
- Helps us to visualize the topology of our network. 
- ![alt text](image-194.png)
- We can see the peerings between the Vnets. 
- If we click on + button for a Vnet we can see the subnets and NSGs inside the Vnet. 
- ![alt text](image-195.png)
- Topology Viewer gives a good high level view of the topology in our Azure environment. 
- ![alt text](image-196.png)

## Securing the VM Access
- ![alt text](image-197.png)
- Both the Catalog VM and Weather API expose public IPs and can be exploited. 
- The larger the attack surface, the greater the risk 
- Leaving public IPs open, is always a risk, which we want to avoid. 
- ![alt text](image-198.png)
### JIT Access
- Just in Time Access
- Open the port for access on demand and automatically close it. 
- Allows access for a limited time.
- Rest of the time - it is closed. 
- Can be configured from VM page's in the portal.
- Requires Security Center License Upgrade. 
- ![alt text](image-199.png)
### VPN
- Secure tunnel to the VNet.
- Can be configured so that no one else can connect to the VNet. 
- Requires VPN Software and license(not part of Azure)
- Makes setup more complicated and expensive
### Jumpbox
- Place another VM in the Vnet
- Allow access only to this Vnet.
- When we need to access one of the other VMs, connect to this one and connect from it to the relevant VM.
- Only one port is open(still kind of a problem...)
- Cost is only the additional VM(the Jumpbox)
- ![alt text](image-200.png)
### Bastion
- A web based connection to the VM
- No open port is required
- Simple and secure
- Costs around 140$/ month. 

## Using Bastion
- ![alt text](image-201.png)
- Also adds a subnet to the Vnet
- ![alt text](image-202.png)
- No need for RDP connection and expose a port. 
- Azure Bastion is a fully managed platform-as-a-service (PaaS) service that provides secure and seamless RDP/SSH connectivity to your virtual machines directly over TLS from the Azure portal or via the native SSH or RDP client on your local computer.
- It eliminates the need for a public IP address on your virtual machines and simplifies network security management.


## Service Endpoint
- A lot of managed services expose Public IP
- examples include Azure Sql Server, App Services, Storage etc. 
- Sometimes these resources are accessed only from resources in the cloud i.e Database in the backend.
- All of this expose security risks 
- Service Endpoint solves this security risk
- Creates a route from the Vnet to the managed service. 
- Traffic never leaves Azure backbone although the resource still has a public IP. 
- Access from the internet can be blocked.
- Good thing it is free.
- Enable Service Endpoint on the subnet from which we want to access the resource. 
- On the resource, set the subnet as the source of traffic. 
- ![alt text](image-203.png)
- ![alt text](image-204.png)
- Resources that support Service endpoint are Storage, PostgresSql, CosmosDb, Key Vault, Service Bus, Event Hub, App Service, Cognitive Services. 


## Private Link
- A lot of managed services expose Public IP
- examples include Azure Sql Server, App Services, Storage etc. 
- Sometimes these resources are accessed only from resources in the cloud i.e Database in the backend.
- All of this expose security risks 
- A newer solution and better solution to this problem. 
- It extends the managed service into the Vnet.
- Traffic never leaves the Vnet.
- Access from the internet can be blocked. 
- Can be used from on-prem networks.
- However, it isnt free. 
- ![alt text](image-205.png)
- ![alt text](image-206.png)
- ![alt text](image-208.png)
- ![alt text](image-209.png)

## Service Endpoint vs Private Link 
- ![alt text](image-210.png)

## App Service Vnet integration.
- Allows access from App Service to resources within Vnet so that resources are not exposed on the internet
- Extremely useful when App Service needs access to a VM with some internal resources. 
- Supports same region Vnets. For Vnets in other regions - a gateway is required.  
- ![alt text](image-211.png)
- ![alt text](image-212.png)
- ![alt text](image-213.png)


## App Service Access Restrictions
- Similar to NSG - but for App Services
- Restricts traffic to App Services
- By default all inbound traffic is allowed to the relevant ports 
- Using access restrictions, inbound traffic is restricted to the allowed IPs/Vnets/Service Tags(general name for an azure managed service like loadbalancer, application gateway) 
- Main Use Cases: 
- ![alt text](image-215.png)
- ![alt text](image-216.png)
- ![alt text](image-218.png)

## App Service Environment(ASE)
- This is a special type of app service deployed directly to a dedicated Vnet. 
- Vnet can be configured like any other Vnet - Subnets, NSGs etc. 
- Created on dedicated hardware. 
- In standard tiers of App Service, we cannot place it inside a specific Vnet. 
- Quite expensive. 
- 1000$/month. 
- Has superb scaling capabilities. 
- ![alt text](image-219.png)
- ![alt text](image-220.png)
- ![alt text](image-221.png)


## Load Balancer
- Azure services that distributes load and checks health of the VMs.
- When VM is not healthy, no traffic is directed to it. 
- Can work with VMs or Scale Set. 
- Can be public or private. 
- Operates at layer 4 of OSI Model 
- ![alt text](image-223.png)
- ![alt text](image-224.png)
- ![alt text](image-225.png)
- Same tuples are used by NSG. 
- ![alt text](image-226.png)
- ![alt text](image-227.png)
- ![alt text](image-229.png)
- ![alt text](image-230.png)
- ![alt text](image-231.png)
- ![alt text](image-232.png)
- ![alt text](image-233.png)
- ![alt text](image-234.png)

## Application Gateway 
- Web Traffic Load balancer with improved web capabilities. 
- Can function as the external endpoint of the webapp.
- Works with VMs, VM Scale Sets
- Also supports App Services and K8s 
- Similar to Load balancer but has few advanced features:
- SSL Termination, Autoscaling, Zone redundancy, Session affinity, URL based routing, Websocket and HTTP/2 support, Custom error pages, Header and URL Rewriting, WAF 
- URL based routing allows us to route requests based on path. 
- Operates at layer 7 of OSI Model 
- It can see the content of the transmission which cannot be done on Load Balancer.
- ![alt text](image-235.png)
- Most important thing is WAF 
- ![alt text](image-237.png)
- In prevention mode, WAF will block incoming traffic. 
- ![alt text](image-238.png)
- ![alt text](image-239.png)
- App GW must be placed in its own subnet.
- Often in its own Vnet. 
- Must make sure backend resources are accessible from App GW Subnet. 
- ![alt text](image-241.png)
- ![alt text](image-242.png)
- ![alt text](image-245.png)
- Just make sure Address spaces of the Vnet created for App GW and the other VMs are not overlapping.
- This is because we are going to peer both the Vnets. 
- ![alt text](image-246.png)
- ![alt text](image-247.png)
- ![alt text](image-248.png)
- ![alt text](image-249.png)
- Define routing rules
- ![alt text](image-250.png)
- ![alt text](image-251.png)
- ![alt text](image-252.png)
- ![alt text](image-253.png)
- Now create the application gateway
- ![alt text](image-254.png)
- ![alt text](image-255.png)
- To protect the App Service, we will use Service Endpoint(alternatively we can use Private Link) 
- ![alt text](image-257.png)
- Now go to App Service 
- Go to Networking and use Access Restrictions to allow traffic only from the service endpoint created above
- ![alt text](image-258.png)
- ![alt text](image-259.png)
- Now access restrictions are setup on the Azure App Service, so now we cannot access the App Service from the internet directly.
- Only way to access it is from the Application Gateway.

## Connecting to VM from Application Gateway 
- Our VM is in a different Vnet
- So we need to first define peering between the App GW Vnet and this VM's Vnet 
- ![alt text](image-260.png)
- ![alt text](image-261.png)
- Copy the private IP Address of the VM 
- In the App GW, go to Backend pools 
- Go to catalog pool 
- Copy the private IP Address of catalog VM
- ![alt text](image-262.png)
- Go to the Network Settings of VM in the NSG and disable the inbound rule for port 8080
- ![alt text](image-263.png)
- We just need this rule:
- ![alt text](image-264.png)
- Now we can access the catalog VM using the App GW only and not using the VM's IP Address
- All traffic to Catalog VM can only come through the Application Gateway. 

## Application Gateway and AKS 
- No built-in integration with AKS 
- AKS has its own gateway( called services)
- There is an Application Gateway Ingress Controller (AGIC) that does this 
- One alternative to App GW is using nginx ingress controller. 

## Application Gateway and Function Apps 
- Function Apps are basically App Services only 
- They can be protected by App GW in the same way as App Services 
- We can configure them in Backend pool and then setup Access Restrictions. 

## Current Architecture so far 
- ![alt text](image-265.png)

## Affinity (in Application Gateway)
- ![alt text](image-266.png)
- This setting makes sure user will always be directed to the same instance(VM/App Service) it began with. 
- Feature should be avoided wherever possible as this will result in one instance being overloaded and others being idle
- Usually used in Stateful apps and is a sign a bad design. 
- Always try to design stateless apps. 

## Stateless Architecture
- Here the application's state is stored in only 2 places: the data store and the user interface. 
- No state is stored in application code. 
- State = Application data 
- ![alt text](image-267.png)
- However this is problematic. 
- One of the problems is scalability.
- Another problem is redundancy(Allows the system to function properly when resource is not working)
- ![alt text](image-268.png)
- Our architecture must look like this 
- ![alt text](image-270.png)
- Stateful applications have a hard time with both scalability and redundancy. 
- ![alt text](image-271.png)
- ![alt text](image-272.png)
- In a stateless architecture we can route the same request as follows:
- ![alt text](image-273.png)
- Always use stateless architecture. 
- Supports scalability and redundancy. 


## Application Gateway and Cookies 
- Usually in front of the App GW, we also have a DNS Server. This DNS Server defines the DNS name of the Web App
- ![alt text](image-274.png)
- What happens when a user tries to browse this website?
- ![alt text](image-275.png)
- In the above scenario, the App Service sends a cookie in the response and it has the domain name of the App Service.
- In this case, the cookie will be dropped by the browser as there is domain name mismatch between the domain name set by DNS and the one defined by the App Service
- ![alt text](image-276.png)
- ![alt text](image-277.png)
- We need to set the domain name of the App Service to the domain name defined by the DNS of App GW 

## Secure Network Design 
- Each layer in the application has its own Vnet. 
- Access to resources must be extremely limited.
- ![alt text](image-278.png)
- Also called Hub and Spoke Model. 
- All connections must go through a NSG. 

### Please note that we cannot define NSG for the App Service, only for Subnets and VM's network interfaces. We can only define Access Restrictions and make sure connections to App Service come through either a Service Endpoint or a Private Link. 

### Also note that Application Gateway is best suited for handling external resources and Load Balancer is more cost effective for internal resources. Using Application Gateway for Internal Resources is probably an overkill

## Azure Data Services 
- Azure provides many data solutions as cloud services like Relational databases, NoSql databases, object stores.
- Fully managed services.
- Can be part of Azure app or completely independent. 
- Various pricing models.
- Always better than unmanaged solutions(no need to care about patching, hotfixes etc.)


### Major Database Features
- What to look for when selecting a database?
- Security -->Network Isolation, Encryption.
- Backup --> Backup Types, Retention Period
- Availability --> SLA, Replication, DR

### Database on a VM
- We have the option to install DB on VM 
- There are ready made VMs in the marketplace. 
- ![alt text](image-279.png)
- Pros are: Full Flexibility(configure DB anyway we want) and it provides Full Control
- Cons are: you have to take care of everything like SLA, Updates, Availability, Security, Backups etc.

### Azure Sql 
- Managed Sql Server on Azure
- Works like any other Sql Server
- Great compatibility with on-prem SQL Server 
- Offers built in security, backup, availability and more.
- Flexible pricing models 
- Comes in many flavors
- ![alt text](image-280.png)

### Azure Sql Database 
- Managed Sql Server on Azure 
- Single database on a single server
- Automatic backups, updates and scaling. 
- Good compatibility with on-prem Sql Server but not all features are supported. 
- For Security it has IP Firewall rules, Service Endpoints, SQL and Azure AD Authentication.
- Secure Communication using TLS
- Data is encrypted by default using TDE(Transparent Data Encryption)
- ![alt text](image-281.png)
- ![alt text](image-282.png)
- ![alt text](image-283.png)
- 2 Compute Tiers 
- ![alt text](image-286.png)
  
### Elastic Pool 
- Based on Azure SQL
- Allows storing multiple databases on a single server 
- Great for databases with low average utilization and infrequent spikes
- ![alt text](image-288.png)
- Note that in the above pic, no 2 databases are experiencing a spike at the same time.
- This makes Elastic Pool very cost effective. 
- Purchase the compute resources we need, not the database.


### Managed Instance
- Closer to the on-prem SQL Server.
- Near 100% compatible with on-prem SQL 
- Can be deployed to Vnet
- Business model close to on-prem one. 
- Main differences with other flavors:
- No active geo-replication
- SLA is 99.99% less than Azure Sql of 99.995%
- Support built-in functions 
- Runs CLR code.
- No autoscaling and tuning. 
- No availability zone compared to Azure SQL 
- No serverless tier.
- No hyperscale( hyperscaling offers superior performance)

## Azure SQL Pricing
 - ![alt text](image-289.png)
 - ![alt text](image-290.png)
 - ![alt text](image-291.png)
 - ![alt text](image-292.png)
 - DTU -> Unit of Compute Power created by Microsoft
 - Roughly 100 DTU is equal to 1 vCore. 
 - ![alt text](image-293.png)
 - ![alt text](image-294.png)
 - ![alt text](image-295.png)
 - ![alt text](image-296.png)
 - ![alt text](image-298.png)

## Which Azure SQL to choose ?
- ![alt text](image-299.png)

## Connecting to Azure SQL Database
- We need to create an Azure Sql Server instance also 
- Then we need to allow our private IP Address access to the Sql database 
- ![alt text](image-300.png)
- We can copy the connection string from the Azure portal and paste it inside the appsettings.json file.
- We can then publish our code and copy paste it to catalog VM
- ![alt text](image-301.png)
- We will get this error: 
- ![alt text](image-302.png)
- For now, we will add the IP Address to the Firewall rules.
- Now it will start working
- ![alt text](image-303.png)

## Securing the Database Connection
- Adding IP Address to the firewall rules to allow access to the database is not the correct way.
- We dont want firewall rule to allow access through private IP address.
- We can use private endpoints which are more secure.
- ![alt text](image-304.png)
- ![alt text](image-305.png)
- ![alt text](image-306.png)
- ![alt text](image-307.png)
- ![alt text](image-308.png)
- We need a DNS zone so that this db server name: Server=tcp:nishantreaditserver.database.windows.net,1433 points to the correct IP Address of the private endpoint. 
- ![alt text](image-309.png)
- By setting up a private DNS zone, it will redirect that server name to the private IP Address and not the public one
- ![alt text](image-310.png)
- Now remove Public Network Access. 
- Now we can connect to the Azure Sql Database server securely from the catalog VM Vnet using the private endpoint which we just configured. 
- Now the connection between catalog VM and Azure Sql is fully secure.

### We can also setup the connection string or application settings directly in the App Service also like this: 
- ![alt text](image-311.png)
- The way to secure a connection from an App Service to any other serverless Azure resource is through Vnet integration. 
- We need to have Vnet integration from App Service to Vnet
- We need to have private endpoint to setup between Vnet and the database. 
- Go to App Services->Networking 
- ![alt text](image-312.png)
- ![alt text](image-313.png)
- There is already a private endpoint defined for readit-app-vnet and the database.


## Cosmos Db
- Fully managed NoSql database
- Amazing performance - <10ms for 99% of operations
- Globally distributed
- Fully automated management -updates,scaling,fixes etc
- Exposes multiple APIs: SQL, Mongo, Gremlin, Azure Table, Cassandra(per account)
- We can choose how to use Cosmos Db, if we are familiar with SQL, we can choose SQL, if we like Mongo, we can choose Mongo 
- Cosmos Db is a hierarchial database 
- ![alt text](image-315.png)
- Can be distributed across many regions
- API automatically picks the closest one.
- When using write replication SLA is 99.9999 % (highest SLA in all Azure)
- Managed automatically, no code changes are required. 
- Full Backup every 1-24 hours(default is 4)
- Retention period 20-30 days (default is 30)
- Supports IP Firewall Rules, Service Endpoints and Private Endpoints
- Supports Azure AD Authentication
- Supports Secure communication using TLS 
- Data is encrypted by default

### Partitions in Cosmos Db 
- Data items are divided into partitions 
- Logical group of items based on a specific property
- For e.g: In a cars database, the Model can be a partition property
- ![alt text](image-316.png)
- In the above we are partitioning the data based on the model of the car. 
- Partitions are the basic scale unit in Cosmos Db.
- When we do scaling up or scaling down in Cosmos Db, what is actually scaled up/down are the partitions. 
- Distributions and scale are per partitions
- Make sure items are divided as evenly as possible. 
- We want to make sure the number of items in each partition are as similar as possible. 
- It is very very important to select the right partition property. 
- This property cannot be modified later. 

## SQL vs NoSQL database 
- Sql are the traditional relational databases like Sql Server, MySql, Oracle. 
- Stores data in tables and tables have concrete set of columns 
- Tables have relationships with each other 
- ![alt text](image-317.png)
- SQL databases have transactions: Atomic set of actions 
- Transactions are ACID. 
- All relational databases are queried using SQL 
- NoSql has its emphasis on scale and performance. 
- NoSql are schemaless. 
- In NoSql data is stored in JSON format. 
- Most NoSql databases support Eventual Consistency. 
- In NoSql database, Data can be temporarily inconsistent. 
- Transactions are the main bottleneck in SQL databases
- In NoSql database, we have no standard for querying. 
- ![alt text](image-318.png)


## Cosmos Db consistency levels
- Traditionally, Relational Dbs have strong consistency: Call returns only after successful commit in all replicas(High availability)
- In No Sql databases, we have eventual consistency: Call returns immediately, commit in replicas happens later(Low latency)
- ![alt text](image-319.png)
- Always have to make a choice. 
- Cosmos Db offers 5 consistency levels:
- ![alt text](image-320.png)
- ![alt text](image-321.png)
- ![alt text](image-322.png)
- ![alt text](image-323.png)
- ![alt text](image-324.png)
- ![alt text](image-325.png)
- ![alt text](image-326.png)
- Consistency levels are configured at the account level.
- But they can be relaxed at the request level 
- If the account level consistency is strong, at the request level we can ask for Bounded Staleness request level. 


## Cosmos Db pricing
- Based on RU/s(Request Unit per second)
- 1 RU = Read item of size 1KB 
- Read = Get item by its ID, not by query
- 1 RU/s = Read 1 item of 1 KB in 1 second
- 400 RU/s = Read 400 items of 1 KB in 1 second 
- UPDATE/DELETE/INSERT/QUERY - More than 1 RU 
- We can see the actual RU consumed in the response header of the results. 
- ![alt text](image-327.png)
- ![alt text](image-328.png)
- ![alt text](image-329.png)
- ![alt text](image-330.png)

## Using Cosmos Db
- ![alt text](image-332.png)
- ![alt text](image-333.png)
- ![alt text](image-334.png)
- ![alt text](image-335.png)
- ![alt text](image-336.png)
- We can do a hierarchial query like this
- ![alt text](image-337.png)
- Note we can change all the other field names but cannot change the partition key field. 
- We can regenerate the keys also 
- ![alt text](image-338.png)
- We also have read-only keys as well 
- The following code saves incoming data to the Cosmos Db 
```c#
 [Function("ProcessOrderCosmos")]
        [CosmosDBOutput(databaseName: "readit-orders", containerName: "orders", Connection = "CosmosDBConnection",CreateIfNotExists =true)]            
        public object Run(
            [HttpTrigger(AuthorizationLevel.Anonymous, "post", Route = null)] HttpRequest req)            
        {
            string requestBody = new StreamReader(req.Body).ReadToEndAsync().Result;

            _logger.LogInformation($"Order JSON: {requestBody}");

            //return "OK";
            var order=JsonSerializer.Deserialize<Order>(requestBody, new JsonSerializerOptions { PropertyNameCaseInsensitive = true })??new Order();
            order.id=Guid.NewGuid().ToString();
            return order;
        }

```
- For the Function App, if we go to AppSettings, we can see the connection string for Cosmos Db Connection is updated 
- ![alt text](image-339.png)
- We can change the consistency level of cosmos db here 
- ![alt text](image-340.png)
- If we want to see how many RU/s were consumed by a query, we can find this number in the Query Status tab in the Data Explorer. 
- ![alt text](image-341.png)

## Azure MySql
- Managed MySql on Azure
- Works like any other MySql database
- Has great compatibility with on-prem databases
- Offers built-in security, backups, availability and more. 
- ![alt text](image-342.png)
- ![alt text](image-343.png)
- ![alt text](image-344.png)
- ![alt text](image-345.png)
- ![alt text](image-347.png)
- ![alt text](image-348.png)
- ![alt text](image-349.png)
- ![alt text](image-350.png)
- Advantage: Offers a lower cost structure for many workloads compared to Azure SQL Database (especially for smaller-scale or predictable workloads) and Azure Cosmos DB (which can get expensive with high-throughput, globally distributed needs).
- Benefit: Budget-friendly for small to medium-sized applications, with flexible pricing tiers (Basic, General Purpose, Memory Optimized).
- Example: For a pharmacy system tracking medication inventory with moderate data volume, Azure MySQL can be cheaper than provisioning Cosmos DB’s Request Units (RUs) or Azure SQL’s vCores.
- Advantage: Native support for web frameworks and CMS platforms (e.g., WordPress, Drupal) that often rely on MySQL.
- Azure Database for MySQL is preferred over Azure SQL and Cosmos DB when your pharmacy management system:
- Uses structured, relational data with moderate scale.
- Operates in a single region with predictable workloads.
- Needs a cost-effective, familiar solution with C# integration.

## Azure Postgres SQL
- Managed PostgresSql on Azure
- Works like any other PostgresSql database using the same tools
- Great compatibility with on-prem PostgresSql database
- Includes Hyperscale deployment
- Offers built-in security, backups, availability and more. 
- ![alt text](image-351.png)
- ![alt text](image-352.png)
- ![alt text](image-353.png)
- ![alt text](image-354.png)
- ![alt text](image-355.png)

## Azure Storage
- It is an Object Store
- Used to store special kind of objects like files, documents, video etc. 
- Massively scalable.
- Accessible via HTTP or HTTPs
- Client libraries for every language.
- Durable and highly available. 
- 5 types of Storage Types
- ![alt text](image-356.png)
- ![alt text](image-357.png)
- ![alt text](image-358.png)
- Azure Blobs --> Object Store(Blob --> Binary large object)
- Great for files, videos, documents, largeTexts etc
- Upto 4.77TB per file, 190TB in preview for a single file!!!
- Extremely cost effective 
- Has great availability options
- Very easy to use (simple API)
- Used in conjunction with SQL/NoSQL databases.
- ![alt text](image-359.png)
- Structure is as follows: 
- ![alt text](image-360.png)
- Containers are logical groups of blobs.
- Azure Blob storage offers great redundancy options
- In Azure Zone = datacenter 
- ![alt text](image-361.png)
- ![alt text](image-362.png)
- ![alt text](image-363.png)
- Failover can be initiated via the Portal, Azure CLI or Powershell. 
- Blobs are uploaded to one of the three tiers:
- ![alt text](image-364.png)
- ![alt text](image-365.png)
- Retrieval time is the same in Hot and Cool tiers. 
- Archival tier doesnot support ZRS, GRS and RA-GRS redundancy. 
- ![alt text](image-366.png)
- Tier is set at account level, but can be modified per blob
- Moving between tiers can be automated by lifecycle rules.

## Azure Blob Storage Pricing
- Pricing is based on 3 factors:
- ![alt text](image-367.png)
- ![alt text](image-368.png)
- ![alt text](image-369.png)

## Using Azure Storage Account
- ![alt text](image-372.png)
- ![alt text](image-371.png)
- ![alt text](image-373.png)
- ![alt text](image-374.png)
- ![alt text](image-375.png)
- ![alt text](image-376.png)
- We have 2 keys to rotate keys so as to regenerate the keys.

### Using Azure Blob Storage .NET Client Library
- The Azure.Storage.Blobs library is part of the Azure SDK for .NET, designed to interact with Azure Blob Storage. It allows you to upload, download, delete, and manage blobs (files) in a scalable, managed storage service. Key features include:
- Support for block blobs, append blobs, and page blobs.
- Asynchronous operations for efficient I/O.
- Integration with .NET Core and .NET Framework.
- Install the following nuget package: 
```shell
dotnet add package Azure.Storage.Blobs
```
### Basic Concepts:
- BlobServiceClient: Entry point to interact with the storage account.
- BlobContainerClient: Manages a specific container (e.g., pharmacy-events).
- BlobClient: Handles individual blobs (e.g., a JSON file like events-20250222.json).

### Connect to Blob Storage
```c#
 using Azure.Storage.Blobs;

string connectionString = "DefaultEndpointsProtocol=https;AccountName=pharmacy-storage;AccountKey=your-key;EndpointSuffix=core.windows.net";
BlobServiceClient blobServiceClient = new BlobServiceClient(connectionString);

```
### Create a Container
- Containers organize blobs, like folders. Create one for pharmacy events
```c#
 async Task CreateContainerAsync()
{
    string containerName = "pharmacy-events";
    BlobContainerClient containerClient = blobServiceClient.GetBlobContainerClient(containerName);
    
    await containerClient.CreateIfNotExistsAsync();
    Console.WriteLine($"Container '{containerName}' created or already exists.");
}
```
### Upload a Blob(e.g Event Hubs Data)
- Store a JSON file with medication events
```c#
  async Task UploadBlobAsync()
{
    string containerName = "pharmacy-events";
    string blobName = "events-20250222.json";
    BlobContainerClient containerClient = blobServiceClient.GetBlobContainerClient(containerName);
    BlobClient blobClient = containerClient.GetBlobClient(blobName);

    string jsonData = @"[
        {""Timestamp"":""2025-02-22T10:00:00Z"",""Medication"":""Aspirin"",""Quantity"":50,""EventType"":""Dispensed""},
        {""Timestamp"":""2025-02-22T12:00:00Z"",""Medication"":""Ibuprofen"",""Quantity"":100,""EventType"":""Received""}
    ]";

    using var stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(jsonData));
    await blobClient.UploadAsync(stream, overwrite: true);
    Console.WriteLine($"Uploaded '{blobName}' to '{containerName}'.");
}

```
### Download a Blob
- Retrieve the JSON file for processing (e.g., LLM training or analytics)
```c#
 async Task DownloadBlobAsync()
{
    string containerName = "pharmacy-events";
    string blobName = "events-20250222.json";
    BlobContainerClient containerClient = blobServiceClient.GetBlobContainerClient(containerName);
    BlobClient blobClient = containerClient.GetBlobClient(blobName);

    BlobDownloadResult download = await blobClient.DownloadContentAsync();
    string jsonContent = download.Content.ToString();
    Console.WriteLine($"Downloaded content: {jsonContent}");
}
```

### List Blobs in a container
- List all event files for batch processing 
```c#
 async Task ListBlobsAsync()
{
    string containerName = "pharmacy-events";
    BlobContainerClient containerClient = blobServiceClient.GetBlobContainerClient(containerName);

    await foreach (BlobItem blobItem in containerClient.GetBlobsAsync())
    {
        Console.WriteLine($"Blob: {blobItem.Name}, Size: {blobItem.Properties.ContentLength} bytes");
    }
}
```

### Delete a Blob
- Clean up old event data
```c#
 async Task DeleteBlobAsync()
{
    string containerName = "pharmacy-events";
    string blobName = "events-20250222.json";
    BlobContainerClient containerClient = blobServiceClient.GetBlobContainerClient(containerName);
    BlobClient blobClient = containerClient.GetBlobClient(blobName);

    await blobClient.DeleteIfExistsAsync();
    Console.WriteLine($"Deleted '{blobName}' from '{containerName}'.");
}

```

### Append to a Blob(e.g Logging Events)
- Use an append blob for continuous event logging
```c#
 async Task AppendToBlobAsync()
{
    string containerName = "pharmacy-events";
    string blobName = "event-log.txt";
    BlobContainerClient containerClient = blobServiceClient.GetBlobContainerClient(containerName);
    AppendBlobClient appendBlobClient = containerClient.GetAppendBlobClient(blobName);

    await appendBlobClient.CreateIfNotExistsAsync();
    string eventData = "2025-02-22T14:00:00Z: Dispensed Aspirin 50\n";
    using var stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(eventData));
    await appendBlobClient.AppendBlockAsync(stream);
    Console.WriteLine($"Appended data to '{blobName}'.");
}

```

### Authentication: Use Azure AD or SAS tokens instead of connection strings for production security:
```c#
 BlobServiceClient client = new BlobServiceClient(new Uri("https://pharmacy-storage.blob.core.windows.net"), new DefaultAzureCredential());
```

### Using Shared Access Signatures(SAS Tokens)
- A shared access signature (SAS) is a URI that grants restricted access rights to Azure Storage resources. You can provide a shared access signature to clients who should not be trusted with your storage account key but whom you wish to delegate access to certain storage account resources. By distributing a shared access signature URI to these clients, you grant them access to a resource for a specified period of time
- ![alt text](image-377.png)
- To provide only read-only access to a particular blob use this 
- ![alt text](image-378.png)
- We can attach the SAS Token to the URL here:
- Example of SAS token
```shell
 https://<storage-account-name>.blob.core.windows.net/<container-name>/<blob-name>?sv=2021-04-10&ss=b&srt=sco&sp=rwdlacx&se=2025-12-31T23:59:59Z&st=2025-01-01T00:00:00Z&spr=https&sig=<signature>

 https://nishant1storage.blob.core.windows.net/storeimages/Screenshot%202025-02-23%20114625.png?sv=2022-11-02&ss=b&srt=o&sp=r&se=2025-02-24T01:02:52Z&st=2025-02-23T17:02:52Z&spr=https&sig=3AKgxAAat6xjlkRLdx9jJkdoekSSXue0lOjWKqG6H8k%3D
 
```
- sv: Storage service version.
- ss: Services (Blob, Queue, Table, File).
- srt: Resource types (Service, Container, Object).
- sp: Permissions (Read, Write, Delete, etc.).
- se: Expiry time.
- st: Start time.
- spr: Protocol (HTTPS).
- sig: Signature.

### Types of SAS Tokens
- Account SAS:
Grants access to multiple resources (e.g., blobs, containers, queues) across the storage account.
Example: Read/write to any blob in any container.
- Service SAS:
Grants access to a specific resource (e.g., a single blob or container).
Example: Read-only access to events-20250222.json.
- User Delegation SAS:
Uses Azure AD credentials (instead of the account key) to sign the token, offering enhanced security via RBAC (Role-Based Access Control).
Example: A pharmacy staff member’s AD identity grants temporary blob access.

### Programmatically creating a SAS token for a specific blob
```c#
 using Azure.Storage.Blobs;
using Azure.Storage.Sas;
using System;

class SasTokenExample
{
    static void Main()
    {
        string connectionString = "DefaultEndpointsProtocol=https;AccountName=pharmacy-storage;AccountKey=your-key;EndpointSuffix=core.windows.net";
        string containerName = "pharmacy-events";
        string blobName = "events-20250222.json";

        // Create BlobClient
        BlobClient blobClient = new BlobClient(connectionString, containerName, blobName);

        // Define SAS permissions and expiry
        BlobSasBuilder sasBuilder = new BlobSasBuilder
        {
            BlobContainerName = containerName,
            BlobName = blobName,
            Resource = "b", // Blob
            StartsOn = DateTimeOffset.UtcNow.AddHours(-1), // Start 1 hour ago
            ExpiresOn = DateTimeOffset.UtcNow.AddHours(24), // Expire in 24 hours
            Protocol = SasProtocol.Https,
        };
        sasBuilder.SetPermissions(BlobSasPermissions.Read); // Read-only

        // Generate SAS token
        string sasToken = sasBuilder.ToSasQueryParameters(new StorageSharedKeyCredential("pharmacy-storage", "your-key")).ToString();
        Uri sasUri = new Uri(blobClient.Uri + "?" + sasToken);

        Console.WriteLine($"SAS URI: {sasUri}");
    }
}

```
- Stored Access Policies: Link SAS to a policy on the container for revocability
```c#
 sasBuilder.Identifier = "policy-name"; // Defined in Azure Portal
```
- Secure Storage: Don’t hardcode account keys or SAS tokens in source code; use Azure Key Vault.

## Networking and Fail Over of Storage Account
- ![alt text](image-379.png)
- ![alt text](image-380.png)
- We also have private endpoint connections
- We can setup private endpoint to storage account also. This means in a particular Vnet, this storage account will have a private IP and resources or VMs in that Vnet can access this storage account through that IP. 
- ![alt text](image-381.png)
- Azure Storage redundancy copies your data so that it is protected from transient hardware failures, network or power outages, and natural disasters.
- ![alt text](image-382.png)

## CDN and Automation
- CDN is a content delivery network and it brings content of the storage account closer to the user.
- There are quite a few CDN locations around the world. 
- When we connect CDN to storage account, then objects in the storage account are replicated to the CDN locations and when we retrieve the object, it is downloaded from the closest CDN. 
- ![alt text](image-383.png)
- After the CDN is configured and its link is generated we can modify the URL 
- ![alt text](image-387.png)
- Now image retrieval is much faster due to CDN
### Lifecycle management 
- Offers a rich, rule-based policy for general purpose v2 and blob storage accounts. Use the policy to transition your data to the appropriate access tiers or expire at the end of the data's lifecycle. A new or updated policy may take up to 48 hours to complete.
- Helps to save on costs and improve performance. 
- ![alt text](image-384.png)
- ![alt text](image-385.png)
- We can see this in the code view also 
- ![alt text](image-386.png)
```json 
 { "rules": 
[ { "enabled": true, "name": "rulefoo", "type": "Lifecycle", 
"definition": 
{ "actions": 
{ "version": 
{ "delete": { "daysAfterCreationGreaterThan": 90 } },
  "baseBlob": 
  { "tierToCool": { "daysAfterModificationGreaterThan": 30 }, 
    "tierToArchive": { "daysAfterModificationGreaterThan": 90 }, 
    "delete": { "daysAfterModificationGreaterThan": 2555 } 
  } },
"filters": { "blobTypes": [ "blockBlob" ], "prefixMatch": [ "container1/foo" ] } } } ] }
```
- The above rule moves the blob to the cool tier after 30 days, to archive tier after 90 days and then deletes the blob after 2555 days
- ![alt text](image-388.png)
- We can also use Azure Storage explorer which is a desktop app to access the Azure Storage Account


## Azure Redis
- Managed Redis on Azure
- Provides very fast in-memory distributed cache.
- Great for short-lived frequently accessed data i.e Shopping Cart, Stock Quotes
- Fully compatible with OSS Redis(community edition) and Enterprise Edition - depends on service tiers
- ![alt text](image-389.png)
- ![alt text](image-390.png)
- Most clients go for Standard or Premium.
- Azure price is based on Tier we select and Memory consumed
- ![alt text](image-391.png)

## Using Azure Redis
- We will store shopping cart items in Redis
- ![alt text](image-392.png)
- It’s highly scalable, secure, and supports a wide range of use cases beyond caching, such as session stores, message queues, and real-time analytics
- In-Memory: Data is stored in RAM, offering sub-millisecond latency.
- Managed: Azure handles provisioning, scaling, updates, and backups.
- Open-Source Compatible: Supports Redis data structures (e.g., strings, hashes, lists, sets) and commands.
- Offers throughput up to millions of requests per second with latencies under 1 ms.
- Ideal for speeding up data access in your pharmacy system (e.g., retrieving medication inventory).
- Vertical Scaling: Increase compute/memory within a tier (e.g., from 1 GB to 53 GB in Standard).
- Horizontal Scaling: Premium and Enterprise tiers support clustering (sharding) for larger workloads (up to 1.2 TB in Premium).
- Geo-Replication: Enterprise tiers allow active-active replication across regions.
- Premium and Enterprise tiers support persisting cache data to Azure Storage (RDB or AOF formats), protecting against data loss.
- Use Cases
- Caching:
Store frequently accessed data (e.g., medication stock levels) to reduce database load.
- Session Store:
Manage pharmacy staff session data for a web portal.
- Message Queuing:
Use Redis lists to queue tasks (e.g., processing medication orders).
- Real-Time Analytics:
Track dispensing trends with RedisTimeSeries (e.g., hourly Aspirin usage).
- Pharmacy Predictions:
Cache Event Hubs data or intermediate results for your LLM/inventory forecasting.
- Using it with c#
- Install the nuget package: 
```shell
 Install-Package StackExchange.Redis
```
- Go to "Create a resource" > "Azure Cache for Redis."
- Choose a tier (e.g., Standard C1), region, and name (e.g., pharmacy-cache).
- Get the hostname (e.g., pharmacy-cache.redis.cache.windows.net) and access key from "Access keys."
```c#
 using StackExchange.Redis;
using System;

class RedisExample
{
    private static Lazy<ConnectionMultiplexer> lazyConnection = new Lazy<ConnectionMultiplexer>(() =>
    {
        string connectionString = "pharmacy-cache.redis.cache.windows.net:6380,password=your-access-key,ssl=true,abortConnect=false";
        return ConnectionMultiplexer.Connect(connectionString);
    });

    static IDatabase Cache => lazyConnection.Value.GetDatabase();

    static async Task Main()
    {
        try
        {
            // Set inventory data
            await Cache.StringSetAsync("inventory:Aspirin", "950");
            await Cache.StringSetAsync("inventory:Ibuprofen", "1100");

            // Get inventory data
            string aspirinStock = await Cache.StringGetAsync("inventory:Aspirin");
            Console.WriteLine($"Aspirin Stock: {aspirinStock}");

            // Increment dispensed quantity
            await Cache.StringIncrementAsync("dispensed:Aspirin", 50);
            string dispensed = await Cache.StringGetAsync("dispensed:Aspirin");
            Console.WriteLine($"Aspirin Dispensed: {dispensed}");

            // Set with expiry (e.g., 1 hour)
            await Cache.StringSetAsync("temp:report", "Daily Report", TimeSpan.FromHours(1));
        }
        catch (RedisConnectionException ex)
        {
            Console.WriteLine($"Connection failed: {ex.Message}");
        }
    }
}
```
- ConnectionMultiplexer: Manages the connection to Redis, reusable across your app.
- StringSetAsync: Stores key-value pairs (e.g., inventory levels).
- StringIncrementAsync: Tracks dispensed quantities atomically.
- Expiry: Temporary data (e.g., reports) auto-deletes after a set time.
- ![alt text](image-393.png)
- Eviction Policy in Redis
- ![alt text](image-394.png)
```c#
//Using Redis
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using catalog.Data;
using catalog.Models;
using Microsoft.AspNetCore.Mvc;
using Microsoft.AspNetCore.Mvc.RazorPages;
using Microsoft.Extensions.Configuration;
using Microsoft.Extensions.Logging;
using ServiceStack.Redis;

namespace catalog.Pages
{
    public class IndexModel : PageModel
    {
        private readonly ILogger<IndexModel> _logger;
        private readonly BookContext _context;
        private readonly IConfiguration _config;

        public IndexModel(ILogger<IndexModel> logger, IConfiguration config, BookContext context)
        {
            _logger = logger;
            _context = context;
            _config = config;
        }

        public void OnGet()
        {
            var books=new List<Book>();

            try  {
                books = _context.Books.ToList();
            }
            catch (Exception ex)  {
                ViewData["Error"]=ex.Message;
                ViewData["books"] = books;
                return;
            }
            
            //UNCOMMENT AFTER ADDING REDIS
            //Get data about the shopping cart
            var client = GetRedisClient();
            var cartItems = client.GetListCount("cart");
            ViewData["cartNo"] = cartItems;

            ViewData["books"] = books;
            
        }

        public IActionResult OnPostAddToShoppingCart()
        {
            // UNCOMMECT AFTER ADDING REDIS
            var client = GetRedisClient();
            var bookId = int.Parse(Request.Form["bookId"]);
                
            if (!client.GetAllItemsFromList("cart").Contains(bookId.ToString()))
            {
                var book = _context.Books.Find(bookId);
                book.InStock--;
                _context.SaveChanges();
            
                client.AddItemToList("cart", bookId.ToString());
            }

            return RedirectToPage();
        }

        public IActionResult OnPostLoad()
        {
            BookLoader.LoadBooks(_context);
            return RedirectToPage();
        }

        private IRedisClient GetRedisClient()
        {
            var conString = _config.GetValue<String>("Redis:ConnectionString");
            var manager = new RedisManagerPool(conString);
            return manager.GetClient();
        }
    }
}


```
- When we want to connect from AKS to Azure Sql, we need to create a private endpoint for Azure SQL. 
- ![alt text](image-395.png)
- ![alt text](image-396.png)
- When we create AKS cluster, a Vnet is automatically created
- We need to create a private endpoint between the AKS vnet and the Azure Sql
- To call an Azure Function Url use this code:
```c#
 try  {
            var client=new HttpClient();
            var result=client.PostAsync(_config.GetValue<String>("OrderFunctionUrl"),new StringContent(json)).Result;
                     
            Console.WriteLine("Order sent, status:" + result);

            if (result.StatusCode==System.Net.HttpStatusCode.NoContent)  {
                ClearCart();
            }
 }

```
- ![alt text](image-397.png)
- ![alt text](image-398.png)


## Selecting the right Data Store
- ![alt text](image-399.png)

## Messaging in Azure 
- Messaging services must be able to handle load, throughput and have great latency 
- They are a core part of every Microservices architecture.
- Azure has 4 fully managed messaging services:
- ![alt text](image-400.png)

## Storage Queue
- Part of Azure Storage Account 
- Simplest Queue implementation 
- Create Queue -> Send Message -> Receive Message 
- No special pricing for Queue, included in Storage Account
- Same availability as Storage Account 
- ![alt text](image-401.png)
- ![alt text](image-402.png)
- ![alt text](image-403.png)
- ![alt text](image-404.png)
- ![alt text](image-405.png)

### Using Storage Queues in .NET 
- Add the following nuget package:
```shell 
 dotnet add package Azure.Storage.Queues
```
- We can use it as follows:
```c#
 using Azure.Storage.Queues;
using Azure.Storage.Queues.Models;
using System;
using System.Threading.Tasks;

class Program
{
    // Replace with your actual connection string from Azure Portal
    private static string connectionString = "DefaultEndpointsProtocol=https;AccountName=youraccount;AccountKey=yourkey;EndpointSuffix=core.windows.net";
    private static string queueName = "myqueue";

    static async Task Main(string[] args)
    {
        await RunQueueDemo();
    }

    static async Task RunQueueDemo()
    {
        try
        {
            // Create a queue client
            QueueClient queueClient = new QueueClient(connectionString, queueName);

            // Create the queue if it doesn't exist
            await queueClient.CreateIfNotExistsAsync();

            // Send a message
            string message = "Hello, Azure Queue!";
            await queueClient.SendMessageAsync(message);
            Console.WriteLine($"Sent message: {message}");

            // Peek at the message (view without removing)
            PeekedMessage[] peekedMessages = await queueClient.PeekMessagesAsync(maxMessages: 1);
            if (peekedMessages.Length > 0)
            {
                Console.WriteLine($"Peeked message: {peekedMessages[0].MessageText}");
            }

            // Receive and process message
            QueueMessage[] messages = await queueClient.ReceiveMessagesAsync(maxMessages: 1);
            if (messages.Length > 0)
            {
                QueueMessage receivedMessage = messages[0];
                Console.WriteLine($"Received message: {receivedMessage.MessageText}");

                // Process the message here...

                // Delete the message after processing
                await queueClient.DeleteMessageAsync(receivedMessage.MessageId, receivedMessage.PopReceipt);
                Console.WriteLine("Message processed and deleted");
            }
        }
        catch (Exception ex)
        {
            Console.WriteLine($"Error: {ex.Message}");
        }
    }
}

```
### Key points about using Azure Storage Queues:

- Connection: Get your connection string from the Azure Portal under your Storage Account's "Access keys" section.
- QueueClient: This is your main interface for queue operations. You can:
- Create queues with CreateIfNotExistsAsync()
- Send messages with SendMessageAsync()
- Peek messages with PeekMessagesAsync()
- Receive messages with ReceiveMessagesAsync()
- Delete messages with DeleteMessageAsync()
- Message Handling:
- Messages can be up to 64KB in size
- Default visibility timeout is 30 seconds (message becomes invisible to other consumers)
- You can set custom visibility timeouts when receiving messages
- Here is an example with more options:
```c#
 // Sending a message with delay
await queueClient.SendMessageAsync(
    message: "Delayed message",
    visibilityTimeout: TimeSpan.FromSeconds(30),  // Hidden for 30 seconds initially
    timeToLive: TimeSpan.FromHours(1)  // Message expires after 1 hour
);

// Receiving with custom visibility timeout
QueueMessage[] messages = await queueClient.ReceiveMessagesAsync(
    maxMessages: 1,
    visibilityTimeout: TimeSpan.FromMinutes(5)  // Give 5 minutes to process
);

```
### Best practices:

- Always handle exceptions as Azure operations might fail due to network issues
- Implement retry logic for transient failures
- Consider poison queue patterns for messages that repeatedly fail processing
- Use message IDs or custom metadata for tracking
- Monitor queue length to manage workload

- For production scenarios we need to do this 
```c#
 public class QueueProcessor
{
    private readonly QueueClient _queueClient;
    private const int MaxRetries = 3;

    public QueueProcessor(string connectionString, string queueName)
    {
        _queueClient = new QueueClient(connectionString, queueName);
    }

    public async Task ProcessMessagesAsync()
    {
        while (true)
        {
            try
            {
                QueueMessage[] messages = await _queueClient.ReceiveMessagesAsync(maxMessages: 32);
                
                foreach (QueueMessage message in messages)
                {
                    int retries = 0;
                    bool processed = false;

                    while (!processed && retries < MaxRetries)
                    {
                        try
                        {
                            // Process your message here
                            Console.WriteLine($"Processing: {message.MessageText}");
                            processed = true;
                        }
                        catch (Exception)
                        {
                            retries++;
                            if (retries == MaxRetries)
                            {
                                // Move to poison queue or handle failure
                            }
                            await Task.Delay(1000 * retries); // Exponential backoff
                        }
                    }

                    await _queueClient.DeleteMessageAsync(message.MessageId, message.PopReceipt);
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine($"Queue error: {ex.Message}");
                await Task.Delay(5000); // Wait before retrying
            }
        }
    }
}

```
- Compared to alternatives like Azure Service Bus (which is more feature-rich but pricier), Storage Queues are dirt cheap and simple:
- You pay per operation and storage used, with no fancy subscriptions.
- Great for straightforward messaging needs without the overhead of complex routing or pub/sub systems.
- Storage Queues aren’t perfect for everything:
- If you need real-time messaging (like chat apps), WebSockets or SignalR are better.
- If you need complex routing or topics/subscriptions, Azure Service Bus or Event Grid might suit you more.
- For massive data streams, consider Event Hubs or Kafka.

## Event Grid 
- Allow building event-based architecture
- Publishes events to interested parties 
- No queue/no order 
- Strong integration with many Azure Services 
- Very cost effective and has the simplest pricing scheme in Azure
- No tiers, High Availability is built in 
- ![alt text](image-406.png)
- ![alt text](image-407.png)
- ![alt text](image-408.png)
- ![alt text](image-409.png)
- Supports upto 10 million events per second 
- ![alt text](image-410.png)
- Strong emphasis on performance 
- ![alt text](image-411.png)  
- ![alt text](image-412.png)
- ![alt text](image-413.png)
- In an Azure Function App, if it is not an HTTP trigger, rather a Blob trigger or Event Grid Trigger, 
  we need to specify a storage account to store its metadata. 
- We can specify this in local.settings.json file like this 
```json 
{
  "IsEncrypted": false,
  "Values": {
    "FUNCTIONS_WORKER_RUNTIME": "dotnet-isolated",
    "AzureWebJobsStorage": "DefaultEndpointsProtocol=https;AccountName=nishstorage98;AccountKey=kUcf42dWVwUV51xadO9ZYJyMp7Z5MumbhxH/tXDzjG4cGNxwXsQ36GEhSbWWuaXSRTmjWQSTy/5o+AStNdNusw==;EndpointSuffix=core.windows.net",
    "CosmosDBConnection": "AccountEndpoint=https://readit-cosmos-nishant.documents.azure.com:443/;AccountKey=2TpF59rE6IBC5l7XxaLvMbHqrb9KbOoz2hXKXW9OroPrsKzIIsTfWK725XjVvfvRTHGu8exkohv0ACDb7ey4mQ==;",
    "StorageConnectionString": "DefaultEndpointsProtocol=https;AccountName=nishantordersreadit;AccountKey=/BZQpJOdZJPTG2GxLpi6oBpCM9gYt8RgJnny0ZiAF5IKQaXDlMyImmHB2KbPEEiiHilYBu9iKH1k+AStj1gygw==;EndpointSuffix=core.windows.net"
  }
}


```
- Here is the code for function app which will process the event grid events 
```c#
using Microsoft.AspNetCore.Http;
using Microsoft.Extensions.Logging;
using System.Text.Json;
using System.Collections.Generic;
using Microsoft.Azure.Functions.Worker;
using Azure.Messaging.EventGrid;
using Azure.Storage.Blobs;
using Azure.Messaging.EventGrid.SystemEvents;

namespace AzureCourse.Function
{    
    public class CosmosOrderFunction
    {
        private readonly ILogger<CosmosOrderFunction> _logger;

        public CosmosOrderFunction(ILogger<CosmosOrderFunction> logger)
        {
            _logger = logger;
        }

        // [Function("ProcessOrderCosmos")]
        // [CosmosDBOutput(databaseName: "readit-orders", containerName: "orders", Connection = "CosmosDBConnection",CreateIfNotExists =true)]            
        // public object Run(
        //     [HttpTrigger(AuthorizationLevel.Anonymous, "post", Route = null)] HttpRequest req)            
        // {
        //     string requestBody = new StreamReader(req.Body).ReadToEndAsync().Result;

        //     _logger.LogInformation($"Order JSON: {requestBody}");

        //     //return "OK";
        //     var order=JsonSerializer.Deserialize<Order>(requestBody, new JsonSerializerOptions { PropertyNameCaseInsensitive = true })??new Order();
        //     order.id=Guid.NewGuid().ToString();
        //     return order;
        // }

          [Function("ProcessOrderCosmos")]
        [CosmosDBOutput(databaseName: "readit-orders", containerName: "orders", Connection = "CosmosDBConnection",CreateIfNotExists =true)]
        public object Run(
            [EventGridTrigger] EventGridEvent eventGridEvent,
            [BlobInput("neworders", Connection = "StorageConnectionString")] BlobContainerClient container)
        {           

            try
            {
                _logger.LogInformation("Function started");
                _logger.LogInformation($"Event details: Topic: {eventGridEvent.Topic}");
                _logger.LogInformation($"Event data: {eventGridEvent.Data.ToString()}");

                string eventBody = eventGridEvent.Data.ToString();

                _logger.LogInformation("Deserializing to StorageBlobCreatedEventData...");
                var storageData = JsonSerializer.Deserialize<StorageBlobCreatedEventData>(eventBody, new JsonSerializerOptions
                {
                    PropertyNameCaseInsensitive = true
                });
                _logger.LogInformation("Done");

                _logger.LogInformation("Get the name of the new blob...");
                var blobName = Path.GetFileName(storageData.Url);
                _logger.LogInformation($"Name of file: {blobName}");

                _logger.LogInformation("Get blob from storage...");
                var blockBlob = container.GetBlobClient(blobName);
                var orderText = blockBlob.DownloadContent().Value.Content.ToString();
                _logger.LogInformation("Done");
                _logger.LogInformation($"Order text: {orderText}");

                var order=JsonSerializer.Deserialize<Order>(orderText, new JsonSerializerOptions { PropertyNameCaseInsensitive = true })??new Order();
                order.id=Guid.NewGuid().ToString();
                return order;
            }
            catch (Exception ex)
            {
                _logger.LogError(ex, "Error in function");
                return null;
            }
        }
    }
}



```
- For the event grid to trigger the function app when a blob is uploaded, we need to specify an Event Grid Subscription like this 
- ![alt text](image-415.png)
- ![alt text](image-416.png)
- ![alt text](image-417.png)
- Upload the Blob file: orderSample.json 
- ![alt text](image-418.png)
- Process the function app which runs as a result of Event Grid Trigger 
- ![alt text](image-419.png)
- Check Cosmos Db 
- ![alt text](image-420.png)
- To upload a blob manually from the shopping cart use this code: 
- This code will upload the blob to the neworders container where the Event Grid will be triggered, which will call the ProcessOrderCosmos function, which will deserialize the order from the blob and add it to Cosmos Db 
```c#
 public void OnPostPlaceOrder()  {
            
            var booksInCart=GetBooksInShoppingCart();
            var order=new Order();
            double total=0;
            order.orderDate=DateTime.Now;
            order.priority=1;
            order.items=new List<OrderItem>();

            foreach (var book in booksInCart)  {
                var item=new OrderItem();
                item.name=book.Name;
                item.id=book.ID;
                item.price=book.Price;
                total+=item.price;
                order.items.Add(item);
            }

            order.total=total;

            var json=JsonConvert.SerializeObject(order);

            Console.WriteLine(json);

            // try  {
            // var client=new HttpClient();
            // var result=client.PostAsync(_config.GetValue<String>("OrderFunctionUrl"),new StringContent(json)).Result;
                     
            // Console.WriteLine("Order sent, status:" + result);

            // if (result.StatusCode==System.Net.HttpStatusCode.NoContent)  {
            //     ClearCart();
            // }

            // ViewData["books"]=new List<Book>();
            // ViewData["OrderStatus"]="sent";
            // }
            // catch (Exception ex)  {
            //     ViewData["OrderStatus"]="Error sending order: " + ex.Message;
            // }

            try  {
                string storageConnection = _config.GetValue<String>("StorageConnectionString"); 
                var blobService=new BlobServiceClient(storageConnection);
                var container=blobService.GetBlobContainerClient("neworders");
                var blobClient=container.GetBlobClient($"order_{Guid.NewGuid().ToString()}.json");
                
                // Prepare stream for upload
                byte[] byteArray=Encoding.ASCII.GetBytes(json);
                MemoryStream stream=new MemoryStream(byteArray);
                
                var resp=blobClient.Upload(stream); 

                Console.WriteLine("Order sent!");

                ClearCart();                

                ViewData["books"]=new List<Book>();
                ViewData["OrderStatus"]="sent";
            }
            catch (Exception ex)  {
                ViewData["OrderStatus"]="Error sending order: " + ex.Message;
            }


        }     

```
- ![alt text](image-421.png)
- ![alt text](image-422.png)
- ![alt text](image-423.png)


## Protecting the Orders Function 
- ![alt text](image-424.png)
- ![alt text](image-425.png)
- Basically we add a rule inside Access Restrictions to allow traffic only from the Event Grid Service Tag 


## Azure Service Bus 
- Fully managed, full blown message queuing service 
- Durable 
- Support point to point messaging(Queue) and pub/sub(Topic) scenarios 
- Combination of Storage queues and Event Grid Topics 
- Compatible with AMQP protocol and JMS 2.0 API (Premium only). Used with Java based systems. 
- ![alt text](image-426.png)
- ![alt text](image-427.png)
- offers advanced features 
- Message Sessions(guarantees FIFO)
- Dead letter queue 
- Scheduled delivery 
- Transactions 
- Duplicate Detection 
- Offers SLA of 99.9% 
- Can be configured for geo-disaster recovery. 
- ![alt text](image-428.png)
- 3 tiers: Basic, Standard, Premium
- ![alt text](image-429.png)
- ![alt text](image-430.png)
- ![alt text](image-431.png)
- ![alt text](image-432.png)

## Using Service Bus 
- Private Endpoints are available only in the Premium Tier. 
- ![alt text](image-433.png)
- ![alt text](image-434.png)
- Code to send the message to the queue:
```c#
  public static string connectionString = "Endpoint=sb://sbdemonishant.servicebus.windows.net/;SharedAccessKeyName=RootManageSharedAccessKey;SharedAccessKey=zQGYImgPo535J75IPEW8q/D46un9zhaVn+ASbAypukY=";
        public static string queueName = "my-items";

        public static async Task Main(string[] args)
        {    
            
            Console.WriteLine("======================================================");
            Console.WriteLine("Press ENTER key to exit after sending all the messages.");
            Console.WriteLine("======================================================");

            // Send message
            await SendMessageAsync();

            Console.Read();
        }

        static async Task SendMessageAsync()
        {
            // create a Service Bus client 
            await using (ServiceBusClient client = new ServiceBusClient(connectionString))
            {
                // create a sender for the queue 
                ServiceBusSender sender = client.CreateSender(queueName);

                // create a message that we can send
                ServiceBusMessage message = new ServiceBusMessage("Test Message");

                // send the message
                await sender.SendMessageAsync(message);
                Console.WriteLine($"Sent a single message to the queue: {queueName}");
            }
        }          
    }
```

## Event Hubs 
- Big data streaming platform and event ingestion service 
- No messaging in the description 
- Basically it is a managed Kafka implementation 
- Can receive millions of events per second 
- ![alt text](image-435.png)
- ![alt text](image-436.png)
- ![alt text](image-437.png)
- ![alt text](image-438.png)
- ![alt text](image-440.png)
- ![alt text](image-441.png)
- ![alt text](image-442.png)

## Using Event Hubs 
- Private access is only available on Dedicated, Premium or Standard namespaces.
- ![alt text](image-443.png)
- Code for Event Hub in C# 
```c#
 class Program
    {
        private const string ehubNamespaceConnectionString = "Endpoint=sb://nishanthub789.servicebus.windows.net/;SharedAccessKeyName=RootManageSharedAccessKey;SharedAccessKey=DEnSU0+7Jzc6JEVZfqeFCU1bvMpn0AcPo+AEhJMAYTM=";
        private const string eventHubName = "my-telemetry";        

        static  async Task Main(string[] args)
        {
            // Read from the default consumer group: $Default
            string consumerGroup = EventHubConsumerClient.DefaultConsumerGroupName;

            // Create an event processor client to process events in the event hub
            var consumer= new EventHubConsumerClient(consumerGroup, ehubNamespaceConnectionString, eventHubName);

            Console.WriteLine("Waiting for messages...");

            while (true)  {
                await foreach (PartitionEvent partitionEvent in consumer.ReadEventsAsync())
                {
                    Console.WriteLine($"Message Received: {System.Text.Encoding.Default.GetString(partitionEvent.Data.Body.Span)}");                    
                }
            }  
        }        
    }

```

## Selecting the right Messaging Service 
- ![alt text](image-444.png)

## Current Architecture so far 
- ![alt text](image-445.png)
- Note that function is now triggered using Event Grid Topic and it is more secure as it only works if the event grid is triggered. 

## Identity Management with Azure AD (Microsoft Entra ID)
- Central Identity and Access Management cloud service
- Used to manage access to thousands of apps (Among them- Azure Portal)
- Secure, Robust and Highly intelligent 
- ![alt text](image-446.png)
- ![alt text](image-447.png)
- ![alt text](image-448.png)

### Tenant 
- A specific instance of Azure AD containing accounts and groups 
- Called also Directory 
- Is not part of subscription hierarchy 
- Exists beside the subscription 
- For new subscriptions, a new tenant is created automatically. 
- A tenant can be assigned to multiple subscriptions 
- ![alt text](image-449.png)
- Azure Active Directory is an external resource that can connect to many apps and one of them is Azure. 

## Using Azure AD 
- Change the name of the default directory like this 
- ![alt text](image-450.png)
- ![alt text](image-451.png)
- Switch between tenants(or directories here)
- ![alt text](image-452.png)

## Users and Groups 
- 2 of the main 3 objects managed by Azure AD(other being Roles)
- Manages and stores the users that are part of the tenant.
- Groups the users in Groups Example: IT Admins, Developers etc. 
- Allows defining roles to groups instead of each user. 
- Create new user 
- ![alt text](image-453.png)
- View SignIn Logs 
- ![alt text](image-454.png)
- Add a new group 
- ![alt text](image-455.png)

## Azure AD Licenses 
- Have great effect on the functionality and price of the Azure AD 
- ![alt text](image-456.png)

## Authentication Type 
- Divided into 3 factors: 
- ![alt text](image-457.png)
- ![alt text](image-458.png)
- ![alt text](image-459.png)
- Two Factor Authentication = "Something you know" + "Something you have"
- ![alt text](image-460.png)
- Hacking fingerprint is more difficult 
- Make sure authentication engine supports 2 factor authentication. 
- Should come out of the box and should not require development 
- This decision affects the end users. 

## Azure AD Security Defaults 
- Increases protection of the organization in the Free tier. 
- Security defaults are basic identity security mechanisms recommended by Microsoft. When enabled, these recommendations will be automatically enforced in your organization. 
- Administrators and users will be better protected from common identity-related attacks.
- It basically adds preconfigured security settings 
- ![alt text](image-461.png)
- Has no additional cost 
- For more fine-grained management, use Conditional Access(P1)
- ![alt text](image-462.png)


## RBAC(Role Based Access Control)
- In the past, authorization was defined per user or per user group 
- ![alt text](image-463.png)
- What happens if David leaves the company? Admin will have to go through all the authorizations of David and remove them one by one. 
- To solve this problem RBAC was implemented 
- ![alt text](image-466.png)
- In order to perform any operation or access any data in Azure, we need to have the right role. 
- ![alt text](image-467.png)
- When we created a new subscription in Azure, we were automatically granted the highest role in Azure called owner. 
- In Azure we generally have 3 types of Roles: Owner, Contributor and Reader. 
- ![alt text](image-468.png)
- ![alt text](image-469.png)
- ![alt text](image-471.png)
- Note that in Azure, the users are defined inside the tenant but the Roles and Authorizations are part of Azure itself. 
- It is always better to assign roles to groups and not individual users. Its easier to maintain. 

## Using Azure Roles
- ![alt text](image-472.png)
- ![alt text](image-473.png)
- ![alt text](image-474.png)
- Earlier when we signed as David Jones, we were not able to do anything in the portal 
- David Jones is part of Azure Architects Group and that group has just been granted Contributor Role over the test-rg resource group 
- Now if we login as David Jones, we can see he has access to test-rg resource group.
- ![alt text](image-475.png)
- Since David Jones has contributor role, he cannot add Role Assignment 
- ![alt text](image-476.png)

## Managed Identities
- The ability to assign Azure AD identity to an Azure Resource. 
- The resource can connect to other Azure resources using this identity. 
- No need to handle credentials(usernames, password etc)
- Two types of Managed Identities:
- System Assigned: Managed by Azure, tied to the resource's lifecycle(when the resource is deleted, so is the identity)
- User Assigned: Managed by the user. Can be assigned to multiple resources, not tied to any lifecycle. 
- Most of the times, we use system assigned identities. 
- We can use system assigned managed identities to give access to the SQL server from our App Service. 
- ![alt text](image-477.png)
- ![alt text](image-478.png)
- ![alt text](image-479.png)
- ![alt text](image-480.png)
- ![alt text](image-481.png)
- Click on Set Admin 
- ![alt text](image-482.png)
- Click on Save 
- Now we can create users inside our sql server database from the external provider 
```sql 
CREATE USER [<appservice-name>] FROM EXTERNAL PROVIDER

ALTER ROLE db_datareader ADD MEMBER [<appservice-name>]

ALTER ROLE db_datawriter ADD MEMBER [<appservice-name>] 

```
- ![alt text](image-483.png)
- Now we will remove the username, password from the connection string specified inside the App Service Configuration and replace it with Managed Identity 
- ![alt text](image-484.png)
- When we save, the App service will restart and we can still connect to the database using Managed Identity and not using username/password and this is much more secure and it is the recommended way to connect between Azure Resources rather than using username/password. 

## Using Azure AD inside applications 
- Azure AD can be used as authentication engine on other applications
- Not just the Azure Portal
- It can be used inside our own application also .
- What is the process to use Azure AD in our application?
- Register the application in Azure AD 
- Add code to use Azure AD as the authentication engine. 
- For App Services, this can be configured via the Portal itself (no code changes required)
- Authentication itself, uses OAuth and JWT. 

## OAuth2.0
- Standard protocol for authentication and authorization.
- Widely used, mainly in web apps. 
### OAuth2.0 components 
- ![alt text](image-485.png)

### OAuth2.0 Flow
- ![alt text](image-486.png)
- Lets see how it works 
- Click on Login. It will ask which authorization server to use
- ![alt text](image-487.png)
- We select Facebook 
- ![alt text](image-488.png)
- It will ask us to Grant Access to the app to access private information. 
- Once we provide access, we can login to Feedly 
- ![alt text](image-489.png)
- For App Registration
- Authorization Server should be familiar with the Resource Server (API)
- Resource Server must register itself with the Authorization Server also called App Registration.
- We can also use Github as an authorization server
- Here is how App Registration works with Github 
- ![alt text](image-490.png)
- We will specify details of the application and specify the Authorization callback URL 
- ![alt text](image-491.png)
- Now application is registered 
- ![alt text](image-492.png)
- We have client ID and client secret 
- Resource server must pass these 2 keys to the authorization server 
- Access Token is a JWT 
- JWT contains the data the server needs in order to authenticate the user 
- JWT has 3 sections:
- Header: type of Token(JWT) and signing algorithm 
- ![alt text](image-493.png)
- Payload - Actual data about the user
- ![alt text](image-494.png)
- Signature
- 3 parts of the JWT are base64 encoded and concatenated with a . 
- ![alt text](image-495.png)


## Configuring Azure AD with the App Service for Authentication 
- Click on Authentication
- ![alt text](image-496.png)
- Add an Identity Provider 
- ![alt text](image-497.png)
- Select Microsoft Identity Provider 
- Create new app registration --> Entity in Azure AD that defines the data required to authenticate to our web app. For e.g it defines the callback URL, the type of token that is going to be used, all other metadata for the authentication. 
- ![alt text](image-498.png)
- ![alt text](image-499.png)
- When we select Current tenant- we mean that only users from this tenant can access this app/ 
- For authentication we need the following settings 
- ![alt text](image-500.png)
- ![alt text](image-501.png)
- Now authentication is enabled for the App Service
- Inside the Microsoft Entra ID also, we can see this App Registration 
- ![alt text](image-502.png)
- ![alt text](image-503.png)
- Note that callback URI is created automatically by the App Service
- ![alt text](image-504.png)
- Notice that we are going to pass the ID Token. 

## Adapting code of the App Service to work with Azure AD    
- When we try to access the app, we will see this screen now
- ![alt text](image-505.png)
- Now we are automatically being requested to login through Azure AD. 
- However now the application running inside the App Service should know about the logged in user also 
- So we need to configure the App to use the Azure AD authentication also 
- Add the following nuget packages to the application 
```shell 
dotnet add package Microsoft.Identity.Web
dotnet add package Microsoft.AspNetCore.Authentication.OpenIdConnect
dotnet add package Microsoft.Identity.Web.UI
```
- Add the following code to Program.cs 
```c#
  // Azure AD authentication support
            services.AddAuthentication(OpenIdConnectDefaults.AuthenticationScheme).AddMicrosoftIdentityWebApp(Configuration.GetSection("AzureAd"));
   // Add support for UI elements of the authentication process
   services.AddRazorPages().AddMicrosoftIdentityUI();  


 //In middleware pipeline add this 
 app.UseAuthentication()
 app.UseAuthorization()        

```
- Inside appsettings.json we have the following:
```json 
{
  "AzureAd": {
    "Instance": "https://login.microsoftonline.com/",
    "TenantId": "TENANT_ID",
    "ClientId": "APP_REGISTRATION_CLIENT_ID",
    "CallbackPath": "/signin-oidc"
  },

```
- ![alt text](image-506.png)
- ![alt text](image-507.png)
- ![alt text](image-508.png)
- To check if the user is logged in, use this code
```c#
  @if (User.Identity.IsAuthenticated)
                {
                    <ul class="nav navbar-nav navbar-right">
                        <li>Hello @User.Claims.First(c=>c.Type=="name").Value!
                        </li>                        
                    </ul>
                }
                else
                {
                    <ul class="nav navbar-nav navbar-right">
                        <li>Anonymous User</li>
                    </ul>
                }

}
```
- To view all the claims about the user in the JWT token use this code:
```c#
 public class ClaimsModel : PageModel
    {
        public IEnumerable<Claim> UserClaims { get; set; }
        public void OnGet()
        {
            UserClaims = HttpContext.User.Claims;
        }
    }


  @if (HttpContext.User.Identity.IsAuthenticated)
            {
                foreach (var c in Model.UserClaims)
                {
                    <tr>
                        <td>@c.Type</td>
                        <td>@(c.Value.Length > 100 ? c.Value.Substring(0, 100) : c.Value)</td>
                    </tr>
                }
            }
            else
            {
                <tr>
                    <td>Current Status</td>
                    <td><strong>Not Authenticated</strong></td>
                </tr>
            }

```
- Now the code correctly identifies the user from the claims in the token 
- ![alt text](image-509.png)
- ![alt text](image-510.png)  
- The aud contains the client ID for the app registration 
- We can see details like name,email of the user 
- To check the JWT token sent from Azure AD use this link: http://<app-service-url>/.auth/me
- ![alt text](image-511.png)


## Azure AD B2C 
- Identity-as-a-service for our application
- A business to customer (B2C) service
- Enable integrating identity services in your app. 
- Allows working with various identity providers 
- Provides various user flows
- Enables customization to these user flows 
- ![alt text](image-512.png)
- Good thing is we can include all these features without really including much code in our application
- Difference between Azure AD and Azure AD B2C 
- Azure AD is an Identity Provider and Azure AD B2C is an identity service(used for signin, signup, reset password etc. )
- ![alt text](image-513.png)
- Azure AD B2C supports various authentication features 
- MFA
- Conditional Access
- Audit Log
- Custom Policies
- Custom Pages
- Azure AD B2C is quite complex to setup and has lot of moving parts 
- Azure AD B2C provides a secure and customizable way for businesses to allow customers to sign up and sign in to their applications. Here’s how it works:
- Sign-Up and Sign-In Options: Customers can use social accounts (e.g., Facebook, Google) or create local accounts with their email addresses and passwords.
- Multi-Factor Authentication (MFA): It supports MFA to enhance security, requiring users to verify their identity with an additional step, like a text message or authenticator app.
- Customizable User Experience: Businesses can fully brand the sign-up, sign-in, and password reset pages to match their own look and feel, ensuring a seamless integration with their applications.
- User Flows and Policies: You can define policies to control how users interact with your app, such as the steps for signing up, signing in, or resetting passwords.


## User Flows in Azure AD B2C
- Azure AD B2C User Flows are predefined policies that simplify the process of implementing common identity scenarios in your applications, such as signing up, signing in, and resetting passwords.
- They act as templates, allowing you to quickly set up secure authentication experiences for your users without needing to build everything from scratch.
- User Flows are built-in, configurable policies in Azure AD B2C that define the steps users go through during identity-related actions.
- Each User Flow is designed for a specific purpose and can be customized to some extent, such as branding or adding basic user attributes.
- They handle the user interface, validation, and interaction with Azure AD B2C, so you don’t have to implement these features manually in your application.
- Here are some common types of User Flows:
- Sign up and sign in: Allows users to create a new account or log in with an existing one.
- Profile editing: Enables users to update their profile information.
- Password reset: Guides users through the process of resetting their forgotten password.
- Sign in only: For scenarios where users already have accounts and just need to log in.
- Create User Flows: Set up the necessary User Flows in the Azure portal under User Flows. For example:
- Create a Sign up and sign in flow named **B2C_1_signup_signin**.
- Create a Password reset flow named **B2C_1_passwordreset**.
- Add authentication to the web app with this code:
```c#
 builder.Services.AddAuthentication(OpenIdConnectDefaults.AuthenticationScheme)
    .AddMicrosoftIdentityWebApp(builder.Configuration.GetSection("AzureAdB2C"));

```
- In the appsettings.json file of our asp.net mvc web app add the following settings:
```json 
 {
  "AzureAdB2C": {
    "Instance": "https://your-tenant-name.b2clogin.com",
    "ClientId": "your-client-id",
    "Domain": "your-tenant-name.onmicrosoft.com",
    "SignUpSignInPolicyId": "B2C_1_signup_signin",
    "ResetPasswordPolicyId": "B2C_1_passwordreset",
    "EditProfilePolicyId": "B2C_1_editprofile"  // Optional
  }
}

```
- Use the [Authorize] attribute to restrict access to authenticated users only.
```c#
 [Authorize]
public class AccountController : Controller
{
    public IActionResult Profile()
    {
        // Only accessible to authenticated users
        return View();
    }
}

```
- Handle Sign-In and Sign-Out:
- Sign-In: When a user tries to access a protected resource (e.g., /Account/Profile), they’ll be redirected to the Azure AD B2C sign-in page defined by the B2C_1_signup_signin flow. After authentication, they’re redirected back to your app.
- Sign-Out: Add a sign-out action to clear the session.
```c#
 public async Task<IActionResult> SignOut()
{
    await HttpContext.SignOutAsync(CookieAuthenticationDefaults.AuthenticationScheme);
    await HttpContext.SignOutAsync(OpenIdConnectDefaults.AuthenticationScheme);
    return RedirectToAction("Index", "Home");
}
```
- Customize User Flows (Optional)
To match your application’s branding:
- In the Azure portal, go to User Flows > Page layouts.
- Upload custom HTML/CSS files to style the sign-in, sign-up, or password reset pages.
- A user clicks "Create Account" or "Login" and is redirected to the B2C_1_signup_signin flow.
- After signing up or signing in, they’re redirected back to your site (e.g., /Home/Index). You can access their claims (e.g., User.FindFirst("emails")?.Value) to display a personalized greeting.
- In your app, the authentication middleware handles redirects to the appropriate User Flow based on the action (e.g., sign-in, password reset), ensuring a seamless experience.


## Current Architecture
- ![alt text](image-515.png)

## Synchronizing Azure AD with On-Prem AD 
- Many organizations want to sync their on-prem Active Directory with Azure AD 
- Useful when organization has apps on-prem and in cloud and want to have a single user base 
- We use Azure AD Connect 
- ![alt text](image-516.png)
- 2 modes of authentication with Azure AD Connect 
- ![alt text](image-517.png)
- There are pros and cons of each approach. Password Hash Sync is useful when the on-prem server is down
- Pass-Through is more secure as the data of the organization is located physically closer to them 

## Monitoring in Azure
- A working app is not enough
- We must know its status, how it performs and when it has problems
- This is done via monitoring
- Azure offers lot of built in monitoring mechanisms
- There is a centralized monitoring hub where all monitoring data is streamed and can be queried or used for triggers 
- Very cost effective in Azure
- Monitoring is based on 2 types of data: metrics and logs
- ![alt text](image-518.png)
- Almost every resource in Azure has "Monitoring" section 
- ![alt text](image-520.png)

## Using Metrics
- We can view metrics of VMs here
- ![alt text](image-522.png)
- ![alt text](image-523.png)
- We can filter metrics also 
- ![alt text](image-525.png)
- We can download metrics file to excel and we can analyze the data further
- We can also define the specific metrics we want to view
- We can see more than one chart in a metric
- We can change chart types also 
- ![alt text](image-526.png)
- We can also view metrics in Azure Application Gateway as to how the backends respond
- ![alt text](image-527.png)
- ![alt text](image-528.png)
- We can add filters also
- ![alt text](image-529.png)


## Azure Dashboard
- We can save metrics to Dashboard 
- ![alt text](image-530.png)
- ![alt text](image-531.png)
- We can customize the dashboard also
- ![alt text](image-532.png)
- ![alt text](image-533.png)
- We can download the dashboard.json file
- ![alt text](image-534.png)
- Using this json file, we can import the dashboard or modify it.
- We can create as many dashboards as we want
- ![alt text](image-535.png)
- We can add widgets to the dashboard.
- ![alt text](image-536.png)
- Dashboards are great way to group together related information which we want to monitor regularly.

## Alerts
- Get notifications about events in our resources
- ![alt text](image-537.png)
- We can get real-time notifications about events in our application
- Alerts has certain components 
- ![alt text](image-538.png)
- ![alt text](image-539.png)
- We can setup alerts for CPU Utilization
- ![alt text](image-540.png)
- ![alt text](image-542.png)
- Next we will create Action Groups: They define what should happen when the alert is triggered. 
- Action Groups are group of recipients who will receive the alert
- ![alt text](image-543.png)
- ![alt text](image-544.png)
- ![alt text](image-545.png)
- ![alt text](image-546.png)
- ![alt text](image-547.png)
- ![alt text](image-548.png)
- ![alt text](image-549.png)
- ![alt text](image-550.png)
- ![alt text](image-551.png)
- ![alt text](image-552.png)


## Logs and Analytics Workspace
- All Azure resource generate logs
- All logs contain data about performance, events, errors etc
- Log records need central repository to be stored and viewed. 
- This is the Log Analytics Workspace.
- This is a central location for storing, organizing and analyzing logs
- Aggregates logs from all connected, monitored resources
- Uses specialized query language to query logs 
- Located in a designated region
- Better be the same region of the resources to save costs 
- ![alt text](image-553.png)
- ![alt text](image-554.png)
- ![alt text](image-555.png)
- We can select the scope of logs
- ![alt text](image-556.png)
- We also need to configure our resources to stream logs to the Log Analytics Workspace.
- ![alt text](image-557.png)
- ![alt text](image-558.png)
- We need to add diagnostic setting to define what will happen with the logs of this resource. 
- ![alt text](image-559.png)
- ![alt text](image-560.png)
- Go back to Log Analytics Workspace
- ![alt text](image-561.png)
- ![alt text](image-562.png)
- ![alt text](image-563.png)
- We can pin specific queries to the dashboard
- ![alt text](image-565.png)
- We can get live results in the dashboard
- ![alt text](image-566.png)
- ![alt text](image-567.png)

## App Service Logs
- For .NET Based code, we need to add an extension to stream ASP.NET Core logs
- ![alt text](image-568.png)
- This extension integrates the logs generated by the code with the Log Streaming page.
- ![alt text](image-571.png)
- Add a diagnostic setting for the App Service so that we can stream logs to Log Analytics workspace 
- ![alt text](image-572.png)
- ![alt text](image-573.png)


## Insights
- Collection of metrics, statistics and insights about the resource. 
- Specific to resource type
- Generated automatically 
- Code-based services(App Services, apps on VM) can integrate application insights into code and gain lot of data about app usage, performance. 
- ![alt text](image-574.png)
- ![alt text](image-575.png)
- ![alt text](image-576.png)

## Setting up Application Insights in ASP.NET Core App
- To leverage Application Insights, we need to enhance our app with logging and custom metrics 
- Install the nuget package:
```shell
dotnet add package Microsoft.ApplicationInsights.AspNetCore
```
- Update Program.cs:
- Add Application Insights to your app’s services and configure logging.
```c#
 var builder = WebApplication.CreateBuilder(args);

// Add Application Insights
builder.Services.AddApplicationInsightsTelemetry();

// Configure logging
builder.Services.AddLogging(logging =>
{
    logging.AddConsole(); // Optional: for local debugging
    logging.AddApplicationInsights();
});

builder.Services.AddControllersWithViews();

var app = builder.Build();

app.UseHttpsRedirection();
app.UseStaticFiles();
app.UseRouting();
app.UseAuthorization();

// Enable Application Insights request tracking
app.UseMiddleware<Microsoft.ApplicationInsights.AspNetCore.RequestTrackingMiddleware>();

app.MapControllerRoute(
    name: "default",
    pattern: "{controller=Home}/{action=Index}/{id?}");

app.Run();

```
- Inject ILogger: Use dependency injection to log in your controllers or services.
```c#
public class HomeController : Controller
{
    private readonly ILogger<HomeController> _logger;

    public HomeController(ILogger<HomeController> logger)
    {
        _logger = logger;
    }

    public IActionResult Index()
    {
        _logger.LogInformation("User visited the home page.");
        try
        {
            // Simulate some work
            _logger.LogWarning("Processing request...");
        }
        catch (Exception ex)
        {
            _logger.LogError(ex, "An error occurred on the home page.");
        }
        return View();
    }
}
```
- Add Custom Metrics
- Inject TelemetryClient: Track custom events or metrics.
```c#
 using Microsoft.ApplicationInsights;

public class HomeController : Controller
{
    private readonly ILogger<HomeController> _logger;
    private readonly TelemetryClient _telemetry;

    public HomeController(ILogger<HomeController> logger, TelemetryClient telemetry)
    {
        _logger = logger;
        _telemetry = telemetry;
    }

    public IActionResult Index()
    {
        _logger.LogInformation("User visited the home page.");
        _telemetry.TrackEvent("HomePageVisited"); // Custom event
        _telemetry.GetMetric("PageLoadTime").TrackValue(new Random().Next(100, 1000)); // Custom metric
        return View();
    }
}

```
- Update appsettings.json (Optional for Local Testing)
- Add an instrumentation key placeholder (you’ll set this in Azure later)
```json
 {
  "ApplicationInsights": {
    "InstrumentationKey": "your-instrumentation-key"
  }
}
```
- Set Up Application Insights in Azure
- In the Azure Portal, go to Create a resource > Search for Application Insights > Create.
- Get Instrumentation Key or Connection String:
- Once created, go to your Application Insights resource > Overview.
- Copy the Connection String (preferred for newer setups) or Instrumentation Key.
- Go to your App Service in the Azure Portal.
- Under Settings, select Application Insights.
- Connect to the existing Application Insights resource you just created.
- In your App Service, go to Configuration > Application settings.
- Add a new setting:
- Name: APPLICATIONINSIGHTS_CONNECTION_STRING
- Value: Paste the connection string from Application Insights.
- Visit your deployed app (https://yourappname.azurewebsites.net).
- Trigger actions (e.g., visit pages, cause errors).
- Wait for Data: It may take a few minutes for telemetry to appear in Application Insights.
- View and Filter Metrics and Logs in Application Insights
- Key Sections:
- Overview: Shows high-level metrics (requests, failures, response times).
- Logs: Use KQL (Kusto Query Language) to query logs and metrics.
- Metrics: Visualize numeric data (e.g., PageLoadTime).
- Failures: See exceptions and failed requests.
- Performance: Analyze request durations and dependencies.
- Sample KQL queries
```shell
# View All Logs
traces
| order by timestamp desc


# Filter by Log Level
traces
| where severityLevel == 2 // Warnings
| order by timestamp desc

# Custom Events 
customEvents
| where name == "HomePageVisited"

# Exceptions 
exceptions
| order by timestamp desc


# Custom metrics
customMetrics
| where name == "PageLoadTime"
| summarize avg(value) by bin(timestamp, 5m)

```
- Pin query results to an Azure Dashboard for real-time monitoring.
- If your app has high traffic, enable sampling to reduce telemetry volume
```c#
 builder.Services.AddApplicationInsightsTelemetry(options =>
{
    options.EnableAdaptiveSampling = true;
    options.SamplingSettings.MaxTelemetryItemsPerSecond = 5;
});
```

## Azure Monitor 
- Central Location for all the monitoring aspects of Azure Resources 
- Provides access to metrics, logs, insights and more
- Has additional capabilities not found in individual resources.
- ![alt text](image-577.png)
- We can select the scope of the logs we want to access.
- We can also view insights:
- ![alt text](image-578.png)
- Application Insights is a great tool to monitor Web applications

## Availability Tests
- Availability tests in Application Insights are a feature of Azure Monitor that allows you to monitor the availability and responsiveness of your web applications from various locations around the world
- These tests send web requests to your application at regular intervals and alert you if your application isn't responding or if the response time is too slow
- There are four types of availability tests:
- Standard test: Checks the availability of a website by sending a single request. It includes features like TLS/SSL certificate validity, HTTP request verb (GET, HEAD, POST), custom headers, and custom data.
- Custom TrackAvailability test: Allows you to create a custom application to run availability tests and send the results to Application Insights using the TrackAvailability() method.
- Multi-step web test (deprecated): Plays back a sequence of web requests to test more complex scenarios. These tests are created in Visual Studio Enterprise and uploaded to the portal.
- URL ping test (deprecated): Validates whether an endpoint is responding and measures performance associated with that response. It also allows for custom success criteria and retries.
- You can create up to 100 availability tests per Application Insights resource. 
- These tests work for any HTTP or HTTPS endpoint accessible from the public internet, including REST APIs that your service depends on
- ![alt text](image-579.png)
- ![alt text](image-580.png)
- ![alt text](image-581.png)
- From the tests, we can go to alert/rules page. An alert is automatically created for us
- ![alt text](image-582.png)
- Go to Action Groups and select an action group name to decide what to do with the Alert. 
- ![alt text](image-583.png)
- We can see the requests and corresponding Response Codes and the time it took for the response and the Run location.


## Resource Tags 
- Resources are organized into Resource Groups
- Sometimes we want more information about resources
- Which environment? Test? Production?
- Which app it belongs
- Which group is responsible for it
- For this we have Resource Tags
- They help us organize resources using name-value pairs 
- Examples:
- Environment: Test
- App: readit 
- Group: the-A-team 
- Tags can be set during creation of resource or after that
- Useful for many scenarios:
- Resource Querying(show all resources of the A team)
- Cost analysis(how much did the test environment cost last month)
- ![alt text](image-584.png)
- We can filter by tags
- ![alt text](image-586.png)
- This way we can see all the resources which have tag of env with value of test. 
- We also have something called Resource Graph Explorer. 
- We can query resources using KQL and using Tags
- ![alt text](image-587.png)
- Make a best practice to assign tags to resources so that we can monitor them later and query for them.

## Cloud Architecture so far
- ![alt text](image-588.png)

## Security in Azure
- Azure offers lot of security measures for its resources
- We need to follow security patterns to avoid security incidents

## VM Security Best Practicies
- Restrict access to VM as much as possible
- Make sure only required ports are open to the internet(22/1389/443/80)
- Limit access to specific IP addresses when possible
- Prefer using Bastion for accessing the VM, so no need for open ports 
- If VM is not public facing, place it in a Vnet that is not connected to the internet 

## Networking Security Best Practices 
- Vnets that contain private resources only-should not be exposed to the internet 
- Always use NSG to restrict access to subnets 
- Use service endpoints/private endpoints to restrict access to the resources 
- Use the Hub and Spoke Security Model 
- ![alt text](image-589.png)
- Only the App GW has access to public internet 

## Database Security Best Practices 
- Use encryption at rest and encryption at transit(usually ON by default)
- Connect DB to relevant Vnet using Service Endpoint/Private Endpoints
- Access DB from the app using Managed Identities only 
- Use DB's firewall rule to restrict external access(only specific IPs should be allowed)

## App Service Security Best Practices 
- Dont expose directly to the internet, use Application Gateway 
- Connect to App GW's Vnet using Service Endpoint/Private Endpoint 
- Use Azure AD for authentication, enforce MFA 
- Use Managed Identity to access other resources when possible 


## KeyVault 
- Many apps have secrets that need to be kept safely: Connection Strings, Keys, Certificates, API Keys 
- Usually kept in configuration files, so not really secure 
- Keyvault stores secrets of various types 
- Very restricted access - needs Azure AD authentication 
- Support Hardware Security Modules (for enhanced security)
- Easily Manageable 
- Accessed via REST API 
- Very cost effective 
- ![alt text](image-590.png)
- Operation = Reading a secret from the key vault. 
- Security: Secrets are encrypted at rest and in transit, with access tightly controlled via Azure AD.
- Centralized Management: Update a secret in one place, and all apps using it get the new value.
- Auditability: Logs track who accessed what and when.
- Integration: Works seamlessly with other Azure services and .NET apps.
- Go to the Azure Portal, create a Key Vault, and note its URI (e.g., https://myvault.vault.azure.net/).
- Add a secret (e.g., name: MyApiKey, value: supersecret123).
- Grant Access:
- Assign your app or user permissions via "Access policies" in the Key Vault (e.g., "Get" secrets).
- Use a service principal or managed identity for your app.
- Install nuget packages 
```shell 
 dotnet add package Azure.Identity
dotnet add package Azure.Security.KeyVault.Secrets

```
- Here’s how to fetch a secret using the SecretClient with a managed identity or service principal.
```c#
 using Azure.Identity;
using Azure.Security.KeyVault.Secrets;
using System;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        string keyVaultUrl = "https://myvault.vault.azure.net/";
        string secretName = "MyApiKey";

        try
        {
            // Authenticate using DefaultAzureCredential (tries managed identity, env vars, etc.)
            var credential = new DefaultAzureCredential();
            var client = new SecretClient(new Uri(keyVaultUrl), credential);

            // Get the secret
            KeyVaultSecret secret = await client.GetSecretAsync(secretName);
            Console.WriteLine($"Secret value: {secret.Value}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"Error: {ex.Message}");
        }
    }
}

```
- DefaultAzureCredential handles authentication flexibly (e.g., via Visual Studio, Azure CLI, or a managed identity).
- SecretClient connects to your Key Vault and retrieves the secret by name.
- Run this locally with az login or deploy it to Azure with a managed identity configured.
- Storing and Updating a Secret
- You can also set or update secrets programmatically (if your app has "Set" permissions).
```c#
 using Azure.Identity;
using Azure.Security.KeyVault.Secrets;
using System;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        string keyVaultUrl = "https://myvault.vault.azure.net/";
        string secretName = "MyApiKey";

        var credential = new DefaultAzureCredential();
        var client = new SecretClient(new Uri(keyVaultUrl), credential);

        try
        {
            // Set a new secret
            string newValue = "newsecret456";
            await client.SetSecretAsync(secretName, newValue);
            Console.WriteLine($"Set secret '{secretName}' to '{newValue}'");

            // Retrieve it to confirm
            KeyVaultSecret secret = await client.GetSecretAsync(secretName);
            Console.WriteLine($"Retrieved secret: {secret.Value}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"Error: {ex.Message}");
        }
    }
}
```
- SetSecretAsync creates a secret if it doesn’t exist or updates it if it does.
- Each update creates a new version of the secret—Key Vault keeps the history.
- Here’s a more practical example: fetching a database connection string from Key Vault for use in a .NET app.
```c#
  using Azure.Identity;
using Azure.Security.KeyVault.Secrets;
using Microsoft.Data.SqlClient;
using System;
using System.Threading.Tasks;

public class DatabaseService
{
    private readonly string _connectionString;

    public DatabaseService(string keyVaultUrl, string secretName)
    {
        _connectionString = GetSecretAsync(keyVaultUrl, secretName).GetAwaiter().GetResult();
    }

    private static async Task<string> GetSecretAsync(string keyVaultUrl, string secretName)
    {
        var credential = new DefaultAzureCredential();
        var client = new SecretClient(new Uri(keyVaultUrl), credential);
        KeyVaultSecret secret = await client.GetSecretAsync(secretName);
        return secret.Value;
    }

    public async Task QueryDatabaseAsync()
    {
        try
        {
            using (var connection = new SqlConnection(_connectionString))
            {
                await connection.OpenAsync();
                Console.WriteLine("Database connection successful!");
                // Your DB logic here...
            }
        }
        catch (Exception ex)
        {
            Console.WriteLine($"DB Error: {ex.Message}");
        }
    }
}

class Program
{
    static async Task Main(string[] args)
    {
        string keyVaultUrl = "https://myvault.vault.azure.net/";
        string secretName = "DbConnectionString";

        var dbService = new DatabaseService(keyVaultUrl, secretName);
        await dbService.QueryDatabaseAsync();
    }
}

```
- The connection string isn’t in your code or config files.
- You can rotate it in Key Vault without redeploying your app.

### Working with Keys and Certificates
- Key Vault isn’t just for secrets—it handles cryptographic keys and certificates too. Here’s how to encrypt data with a key
```c#
 using Azure.Identity;
using Azure.Security.KeyVault.Keys;
using System;
using System.Text;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        string keyVaultUrl = "https://myvault.vault.azure.net/";
        string keyName = "MyEncryptionKey";

        var credential = new DefaultAzureCredential();
        var keyClient = new KeyClient(new Uri(keyVaultUrl), credential);

        try
        {
            // Get the key (assumes you’ve created an RSA key in Key Vault)
            KeyVaultKey key = await keyClient.GetKeyAsync(keyName);
            var cryptoClient = new CryptographyClient(key.Id, credential);

            // Encrypt some data
            string plaintext = "Sensitive data";
            byte[] plaintextBytes = Encoding.UTF8.GetBytes(plaintext);
            EncryptResult encryptResult = await cryptoClient.EncryptAsync(EncryptionAlgorithm.RsaOaep, plaintextBytes);
            Console.WriteLine($"Encrypted: {Convert.ToBase64String(encryptResult.Ciphertext)}");

            // Decrypt it
            DecryptResult decryptResult = await cryptoClient.DecryptAsync(EncryptionAlgorithm.RsaOaep, encryptResult.Ciphertext);
            string decryptedText = Encoding.UTF8.GetString(decryptResult.Plaintext);
            Console.WriteLine($"Decrypted: {decryptedText}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"Error: {ex.Message}");
        }
    }
}
```
- Authentication: Prefer managed identities over client secrets for Azure-hosted apps.
- Error Handling: Retry on transient failures (e.g., network issues) with libraries like Polly.
- Caching: Cache secrets in memory to reduce Key Vault calls, but refresh periodically.
- Access Control: Use least-privilege policies—don’t give blanket permissions.
- Rotation: Rotate secrets and keys regularly, and use Key Vault’s versioning to manage transitions.


## Configuring the KeyVault
- Setup the Keyvault on the Azure Portal
- Set up Access Policy as Azure RBAC 
- ![alt text](image-591.png)
- Add Diagnostic Settings for the keyvault and collect logs from this into the Log Analytics Workspace
- To view secrets in the keyvault add a role assignment of Key Vault security officer to yourself
- ![alt text](image-592.png)
- Now we can add the secret like this 
- ![alt text](image-593.png)
- In the appsettings.json of our catalog project add this and remove the BooksDb connection string 
```json
 {
  
  "KeyVault":{
    "BaseUrl": "https://nishantkeyvault1985.vault.azure.net/"
  }
}


```
- To configure Key vault in catalog project add this nuget package:
```shell
 dotnet add package Microsoft.Extensions.Configuration.AzureKeyVault

```
- Now setup Program.cs file to use the Azure Key vault like this 
```c#
 public static IHostBuilder CreateHostBuilder(string[] args) =>
            Host.CreateDefaultBuilder(args)
                .ConfigureWebHostDefaults(webBuilder =>
                {
                    webBuilder.UseStartup<Startup>()
                    .ConfigureAppConfiguration((ctx, builder)=>  {
                        var config=builder.Build();
                        builder.AddAzureKeyVault(config["KeyVault:BaseUrl"]);
                    });

                });
    }

```
- Now publish the code 
- Upload the code to catalog VM
- If we directly run the code from the VM it will not work
- This is because we are yet to allow access from the VM to the Key Vault. 
- ![alt text](image-594.png)
- Catalog VM must have a role that allows it to access the secrets from the KeyVault
- Assign a Managed Identity to the VM 
- ![alt text](image-595.png)
- Add a role assignment to the catalog VM managed identity 
- Catalog VM just needs to read the secrets so we will assign the role of Key Vault Secrets User 
- ![alt text](image-596.png)
- This role allows only reading of Key Vault contents
- ![alt text](image-597.png)
- Now restart the IIS 
- Now everything works fine 
- ![alt text](image-598.png)
- We can also see insights of the KeyVault like this 
- ![alt text](image-599.png)
- Even though KeyVault is a cloud resource, you can actually use it from on-prem apps too. All you need to do is register the app in Azure AD, and so making it identifiable, and then add an access policy to the KeyVault allowing access to this identity.
- KeyVault has an automatic fail-over mechanism, so that in the rare case of a complete region shut-down, requests to KeyVault are automatically routed to the paired region, where its data is replicated. You won't even know about it...


## Defender for the Cloud(earlier called Security Center)
- Central location for monitoring and alerting security related issues 
- Displays a summarized list of problems found in the subscriptions resources
- In some cases, allow a single click fix 
- ![alt text](image-600.png)
- We can see recommendations 
- ![alt text](image-601.png)
- ![alt text](image-602.png)
- Looks like Snyk
- ![alt text](image-603.png)
- We can look at Security Alerts also 
- ![alt text](image-604.png)

## Current Architecture 
- ![alt text](image-605.png)

### To protect traffic from Vnets to Managed Services(like App Service), always use Private endpoints since they create a private IP inside the Vnet and donot use public IP and hence are more secure than Service Endpoints 

## Disaster Recovery in Azure 
- A plan to recover from a complete shutdown of a Region 
- Some apps require it, some dont 
- Might have substantial cost aspects 
- Complete shutdown of a region is extremely rare 
- How to setup DR 
- ![alt text](image-606.png)
- ![alt text](image-608.png)
- ![alt text](image-609.png)

## DR Concepts 
- Hot/Cold DR 
- ![alt text](image-610.png)
- ![alt text](image-611.png)
- RPO/RTO (Recovery Point Object, Recovery Time Object )
- RPO --> Data
- RTO --> Time
- ![alt text](image-612.png)
- ![alt text](image-613.png)


## Basics of DR Implementation 
- if RTO is low, we need Active Resources, if it high we can have Passive Resources 
- if RPO is low, we need data synchronization, if RPO is high, we need Backup 
- ![alt text](image-615.png)
- ![alt text](image-616.png)

## DR of Data in Azure 
- Main question when designing the DR of data is: What is the RPO (Or how much data loss can we tolerate)
- If RPO = 0(i.e no data loss in case of disaster)
- We need database that always syncs with the secondary region 
- Currently 3 such databases in Azure 
- Azure SQL(with Geo Replication and Failover Group)
- Cosmos DB(with multi-region account)
- Azure Storage(with GRS redundancy)
- ![alt text](image-617.png)
- ![alt text](image-618.png)
- ![alt text](image-619.png)
- ![alt text](image-620.png)
- ![alt text](image-621.png)
- Note we can select the backup from the most recent Geo redundant server. 
- The RPO here, is minimum 5 minutes(i.e the backup frequency)
- The second example is much cheaper, we dont need a secondary active database when the primary is active. 

## DR of Compute in Azure 
- Main question when designing the DR of compute is: What is the RTO(or how much downtime can we tolerate?)
- If RTO = 0 (no downtime in case of disaster, compute in secondary region must always be up and running)
- ![alt text](image-622.png)
- If RTO > 0(some downtime is tolerated)
- ![alt text](image-623.png)
- ![alt text](image-624.png)
- ![alt text](image-625.png)
- Second example is much cheaper, no secondary active compute is needed when primary is active 
- If RTO is 0, we pay twice both for primary and secondary region resources 
- If RTO > 0, we only pay once. 

## Routing in DR 
- During DR, users should be routed to secondary region 
- ![alt text](image-626.png)
- ![alt text](image-627.png)
- ![alt text](image-628.png)
- ![alt text](image-629.png)
- For automatic routing in case of DR, Azure has 2 main services: Azure Traffic Manager and Azure Front Door 


## Azure Traffic Manager 
- DNS-based traffic load balancer 
- Enables Traffic Distribution across global Azure regions 
- Provides high availability and responsiveness 
- ![alt text](image-630.png)
- 6 Algorithms for Routing in Traffic Manager 
- ![alt text](image-631.png)
- Priority Algorithm helps us in case of DR. 
- ![alt text](image-632.png)
- Very Cost Effective. 
- ![alt text](image-633.png)
- ![alt text](image-634.png)
- ![alt text](image-635.png)
- ![alt text](image-636.png)
- Observe the Failover settings: These settings basically describe how frequently the Traffic Manager will look at the health probes of the endpoints 
- If there is a problem with the endpoint and if it persists across 3 failures, we will route it to the secondary endpoint(DR)
- Go to Endpoints in Traffic Manager 
- Add the endpoints 
- ![alt text](image-637.png)
- Create a new App Service which will be the DR site of the first App Service(Choose a different region)
- ![alt text](image-638.png)
- So now we have 2 App services, original one and the DR one 
- Add another endpoint to Traffic Manager (set Priority to 2)
- ![alt text](image-639.png)
- Now stop the first App Service(we are simulating a region shutdown)
- Now Azure Traffic Manager will route traffic automatically to the secondary endpoint. 
- ![alt text](image-640.png)
- Note we are still using the same URL, but DR now works automatically. 

## Azure Front Door 
- Global entry point for web apps 
- Works on Layer 7(HTTP/HTTPS)
- Multiple routing methods 
- Similar to Application Gateway but on Global Scale 
- Here we have the following features 
- URL- path based routing 
- Session affinity 
- SSL offloading 
- Web Application Firewal (WAF) integration 
- URL Rewrites
- HTTP/2 support 
- Similar to Application Gateway 
- ![alt text](image-641.png)
- Create Front Door Profile 
- ![alt text](image-642.png)
- Now Azure Front Door also includes CDN 
- We will go with Azure Front Door Classic. 
- ![alt text](image-643.png)
- Similar to Application Gateway 
- ![alt text](image-644.png)
- ![alt text](image-645.png)
- ![alt text](image-646.png)
- Add the second backend also (set priority to 2)
- ![alt text](image-647.png)
- Change Probe interval to 10 seconds and set sample size to 1 (means that after 1st failure, front door will route to app service)
- ![alt text](image-648.png)
- Now lets setup routing rules 
- ![alt text](image-649.png)
- now front door is created
- ![alt text](image-650.png)
- Now simulate a DR scenario and stop the first App Service 
- Now Front Door will automatically route to the secondary App Service 
- ![alt text](image-651.png)
- Direct access to the App Service should not be allowed
- Traffic to the App Service should come directly from Azure Front Door 
- Go to the App Service and add an Access Restriction 
- ![alt text](image-652.png)
- ![alt text](image-653.png)
- If we try to access the app service directly, then we will get 403 Forbidden error 
- Now traffic is only allowed through FD 

## Traffic Manager vs Front Door 
- ![alt text](image-654.png)

## Current Architecture so far
- ![alt text](image-655.png)

## Managing Costs in Azure 
- Costs should be Transparent, Predictable and Monitored 
- Avoid Surprises
- Azure Cost Management is central hub for all cost aspects 
- It can make predictions 
- Enable alerts 
- Can manage costs of resources outside Azure like AWS or GCP 
- ![alt text](image-656.png)
- ![alt text](image-657.png)
- Application Gateway is one of the most expensive services in Azure 
- ![alt text](image-658.png)
- We can even filter by Location and Dates to view the Cost Analysis 
- We can also view costs per resource group.
- We can define budgets for our subscription
- We can also specify alerts when we cross 90% of our budget 
- We can also take a look at advisor recommendations
- ![alt text](image-659.png)


## Azure Policy
- Enforcing organizational standards and compliance at scale is not simple 
- However it is important to do so in the cloud
- Role based access helps a little, but it is not enough. More concerned with the permission aspect not the resource itself. 
- We might have requirements like: 
- ![alt text](image-660.png)
- So we need Azure Policy 
- ![alt text](image-661.png)
### When are policies evaluated ?
- ![alt text](image-662.png)
### What happens with non-compliant resources ?
- ![alt text](image-663.png)

## Azure Policy Concepts 
- ![alt text](image-664.png)
- ![alt text](image-665.png)
- ![alt text](image-666.png)

## Adding a new Initiative
- ![alt text](image-667.png)
- Add a new policy definition
- ![alt text](image-668.png)
- ![alt text](image-669.png)
- ![alt text](image-670.png)
- Define the Policy Parameters like define the locations for the location policy
- ![alt text](image-671.png)
- ![alt text](image-672.png)
- Now once the initiative is created, we need to assign it to a scope(i.e where this initiative will take effect)
- ![alt text](image-673.png)
- ![alt text](image-674.png)
- If any VM is created which violates this initiative, we will deny its creation.


## Custom Policies 
- We can create our own policies also 
- But first look closely at existing definitions and samples 
- Policy definitions are JSON based documents 
- They describe various properties of the policy and the rule 
- ![alt text](image-675.png)
- The above policy denies the creation of storage accounts where HTTP traffic is allowed
- We have a condition with 2 condition in it
- We have a policy rule that has this condition which use the parameters of effectType. 
```json 
 {
    "properties": {
        "displayName": "Deny storage accounts not using only HTTPS",
        "description": "Deny storage accounts not using only HTTPS. Checks the supportsHttpsTrafficOnly property on StorageAccounts.",
        "mode": "all",
        "parameters": {
            "effectType": {
                "type": "string",
                "defaultValue": "Deny",
                "allowedValues": [
                    "Deny",
                    "Disabled"
                ],
                "metadata": {
                    "displayName": "Effect",
                    "description": "Enable or disable the execution of the policy"
                }
            }
        },
        "policyRule": {
            "if": {
                "allOf": [
                    {
                        "field": "type",
                        "equals": "Microsoft.Storage/storageAccounts"
                    },
                    {
                        "field": "Microsoft.Storage/storageAccounts/supportsHttpsTrafficOnly",
                        "notEquals": "true"
                    }
                ]
            },
            "then": {
                "effect": "[parameters('effectType')]"
            }
        }
    }
}

```
- ![alt text](image-676.png)
- Now we can assign a policy definition to a resource group 
- ![alt text](image-677.png)
- Now we can look at Compliance section 
- ![alt text](image-678.png)
- We can see the non-compliant resources 
- ![alt text](image-679.png)
- ![alt text](image-680.png)

## What happens when we create a resource that violates a policy 
- ![alt text](image-681.png)
- We cannot select any other size for the VM as the policy restricts us
- ![alt text](image-682.png)
- We can see policy affects creation of a new virtual machine. 
- We can also try creating a storage account that allows HTTP traffic also 
- ![alt text](image-683.png)
- We get this error: 
- ![alt text](image-684.png)

## Containers in Azure 
- In Azure we have Azure Container Apps 
- This service combines the power and flexibility of Azure Kubernetes Services (AKS) with simplicity and ease of use, and provides unmatched way of working with containers in Azure, while providing also autoscaling, logging, monitoring and security.
- Azure offers various services for working with containers 
- Azure container apps is the newest container based services 
- ![alt text](image-686.png)
- Azure Open Shift offers max control but requires time and effort to setup. On the other hand, Azure Function Apps are the easiest to setup but offers little control over the underlying container 


## Containers in Azure Functions 
- Azure functions can be deployed as a Linux container
- Function code is containerized and pushed to the registry 
- Function pulls the image from registry and runs it 
- Takes advantage of all Function app capabilities like:
- Serverless, autoscaling, authentication and more. 


## Azure container instance 
- Simple and effective container runtime environment 
- Just upload the container and it runs 
- No complex configuration 
- No advanced capabilities like autoscaling etc. 

## Containers in App Service 
- Web App for container capability supports containers in App Service 
- Pulls the container from the registry and it runs in App Service 
- Takes advantage of all the App Service capabilities like Autoscaling, load balancing, authentication and more. 


## Azure Kubernetes Service (AKS)
- Fully managed K8s in the cloud 
- Supports all of K8s capabilities 
- No need to deal with virtual machines 
- Supports automatic upgrade 


## Azure Red Hat OpenShift
- Fully managed Red Hat OpenShift platform 
- Built on top of K8s and adds a lot of features 
- Offers lot of automation, no need to deploy yaml files or docker files, we can just directly deploy from github directly to Azure Red Hat Open Shift
- Also offers a developer console and CLI to talk directly to the worker nodes running the app
- Offers high availability 
- Over the air upgrades
- Joint engineering effort from Microsoft and Red Hat. 

## Azure Container Registry 
- Fully managed registry for Docker images
- Geo replicated
- Can build the images 
- Can scan images for vunerabilities 
- Used by all container services in Azure 

## Azure Container Apps 
- ![alt text](image-687.png)
- Sits somewhere in the middle 
- Gives good control and is also easy to use and hence support productivity
- Azure Container Apps is a PaaS offering that lets you deploy and run containers with automatic scaling, minimal configuration, and built-in features like traffic splitting and observability. It abstracts away much of the Kubernetes complexity, sitting between raw Azure Kubernetes Service (AKS) and fully serverless Azure Functions.


## Azure Container Apps 
- Build and deploy fully managed apps and microservices using serverless containers 
- No need for K8s or underlying infrastructure 
- Supports sophisticated autoscaling with KEDA
- Has ingress configuration for traffic security 
- Inter-service communication with Dapr 
- Rich logging and monitoring 
- SLA is 99.95% 

### Scenarios Supported 
- With container apps, we can deploy various types of apps 
- ![alt text](image-688.png)
- It can even run background processes using Azure Container Jobs 


## Architecture of Container Apps 
- ![alt text](image-689.png)
- Environment in Container Apps: Boundary around one or more container app 
- Powers the underlying infrastructures
- Provides the Vnet used by container apps 
- We can use an existing Vnet 
- Provides unified logging and monitoring 
- Environment handles OS upgrades, scale, failover, balancing and more. 
- We can use Auto-generated Vnet or existing Vnet  
- Note that generated vnet cannot access other resources in other vnets 
- ![alt text](image-690.png)
- We also need to decide to choose between single environment or multiple environments for container app
- ![alt text](image-691.png)
- We also need to know about Environment Types 
- ![alt text](image-692.png)
- Creating Environment 
- Environments are created as part of Container Apps deployment 
- Can also be created separately 


## Container App
- Where the container actually runs 
- Uses the environment's resources like networking, logging, security 
- Main entry point in the portal  
- Has its own revision, replicas etc 

## Revision 
- Manages the version of the container app 
- Container app runs a revision or it runs a specific version of the container app 
- Each revision is a snapshot of the version that was deployed 
- Once deployed-cannot be changed 
- Every deployment creates a new revision 
- Up to 100 revisions per container app 

## Revision Characteristics 
- Multiple revisions can be active, allowing traffic splitting between revisions 
- ![alt text](image-693.png)
- What is traffic splitting 
- When multiple revisions are active, traffic can be split between them 
- Very useful for various deployment scenarios like Rolling deployment 
- In Rolling deployment, instances are updated gradually in batches 
- Only if no errors are found, the deployment resumes  
- Initially we have version v1 running 
- ![alt text](image-694.png)
- Then we update one instance of the app with v2 
- ![alt text](image-695.png)
- If there are no errors we update the second instance 
- ![alt text](image-696.png)
- If again there are no errors we update the third instance 
- ![alt text](image-697.png)
- ![alt text](image-698.png)
- We split the traffic incrementally and then move all traffic to v2 and deactivate the older revision 
- Specific revision can be directly accessed 
- Done using a specific URL 


## Replica 
- Azure Container Apps can scale out automatically as needed 
- Done by adding or removing replicas 
- Each replica is an instance of a revision 
- Replica provides the compute and memory for running the revision 
- Upto 300 replicas per revision 


## Underlying Components of Container Apps 
- Azure Container apps use open source components for providing multiple services 
- These components are optional and dont have to be used 
- Add real value to the Container App deployed 
- ![alt text](image-699.png)
- Kubernetes (via KEDA)
- Role: The core orchestration engine.
- Details: Azure Container Apps runs on Kubernetes, managed by Azure, but you don’t interact with it directly (no kubectl needed). It uses KEDA (Kubernetes Event-Driven Autoscaling) to handle scaling based on events or metrics (e.g., HTTP traffic, queue length).
- Why It Matters: You get Kubernetes’ robustness—pods, scheduling, networking—without managing clusters or nodes.
- Example: A .NET app in a container scales up when HTTP requests spike, thanks to KEDA’s HTTP scaler.
- Dapr (Distributed Application Runtime)
- Role: Simplifies microservices development.
- Details: Built-in support for Dapr, an open-source framework, provides features like service invocation, state management, pub/sub messaging, and secret management. 
- Each Container App gets a Dapr sidecar (a companion container) if enabled.
- Why It Matters: Makes it easy to build resilient, distributed apps without rewriting code for every platform.
```c#
 using Dapr.Client;
using Microsoft.AspNetCore.Mvc;

[ApiController]
[Route("api/[controller]")]
public class OrderController : ControllerBase
{
    private readonly DaprClient _daprClient;

    public OrderController(DaprClient daprClient)
    {
        _daprClient = daprClient;
    }

    [HttpPost]
    public async Task<IActionResult> CreateOrder([FromBody] Order order)
    {
        // Publish to a message queue via Dapr
        await _daprClient.PublishEventAsync("pubsub", "new-order", order);
        return Ok("Order published");
    }
}

public record Order(int Id, string Item);

```
- Envoy is an open-source, high-performance proxy designed for cloud-native applications. In Azure Container Apps, it serves as the ingress controller and plays a central role in managing external traffic and service-to-service communication.
- What Envoy Does
- HTTP Ingress:
- Acts as the front door for external traffic, handling HTTPS termination, routing, and load balancing to your containerized apps.
- Supports features like custom domains, TLS certificates (automatic or Bring Your Own), and traffic splitting (e.g., 70% to v1, 30% to v2).
- Example: Your .NET app at myapp.westus.azurecontainerapps.io gets its HTTPS traffic routed by Envoy.
- Service Mesh Lite (via Dapr):
- When you enable Dapr in Container Apps, Envoy often works alongside Dapr’s sidecar to manage service-to-service communication.
- Handles retries, timeouts, and circuit breaking for internal calls, enhancing resilience.
- Example: A .NET microservice calling another via Dapr’s InvokeServiceAsync might route through Envoy under the hood.
- Observability:
- Generates logs and metrics (e.g., request latency, status codes) that feed into Azure Monitor/Log Analytics.
- Example: You can trace a slow API call back to Envoy's logs.
- Azure manages Envoy as part of the Container Apps Environment (the isolated boundary for your apps).
- You don’t configure Envoy directly—Azure abstracts it, exposing only high-level settings (e.g., ingress rules in the Portal or CLI).
- With Envoy in the mix, here’s the updated list of key components:

- Kubernetes (via KEDA):
Orchestrates containers, with KEDA driving event-based scaling (e.g., HTTP, queues).
Envoy slots in as the ingress controller within this Kubernetes backbone.
- Azure Container Instances (ACI):
Provides the compute for running container workloads, likely hosting both app containers and Envoy instances.
- Dapr (Distributed Application Runtime):
Adds microservices capabilities (pub/sub, state, secrets).
Works with Envoy for internal traffic management when Dapr is enabled.
- Container Runtime:
Executes your app’s container images (e.g., Docker-based).
- Envoy Proxy:
Manages ingress (external traffic) and potentially internal service mesh traffic with Dapr.
Handles TLS, routing, and load balancing.
- Container Apps Environment:
A secure, VNet-backed boundary with shared resources (e.g., Envoy ingress, Log Analytics).
- Observability (Azure Monitor + Log Analytics):
Collects logs and metrics from Envoy, Dapr, and your app.
- Storage and Secrets:
Integrates Azure Files and Key Vault, often via Dapr.


## Pricing of Container Apps 
- Depends on the plan used 
- There are only 2 plans: Consumption and Dedicated 
- ![alt text](image-700.png)
- ![alt text](image-701.png)
- ![alt text](image-702.png)
- ![alt text](image-703.png)

## Running a Container App 
- We will host a WorldTrip Application 
- Its architecture is as follows: 
- ![alt text](image-704.png)

## Deploying Container Apps 
- Container Apps always pulls docker image from registry 
- Can be Azure Container Registry(ACR) or other public registries like Docker Hub, Github etc 
- Deployment to Container Apps supports various scenarios 

### Deploy Source Code to Registry 
- Source code is manually packaged and pushed to container registry 
- Container App is deployed, configured to pull the new repository 
- Provides full control on the resources created 
- ![alt text](image-705.png)

### Deploy Source code directly to Container App 
- Source code is directly deployed to container app 
- A registry is automatically created as part of the process 
- Quick and easy, though limited control on resources 
- ![alt text](image-706.png)

### Deploy Existing image to Container App 
- An existing image is pulled by Container App 
- Great for reusing images 
- ![alt text](image-707.png)

### Deployment Tools 
- Deployment can be done by: 
- Azure CLI 
- Using VSCode extensions 
- Cannot be done from Azure Portal 

## Deploying the Container App 
- Create a container registry 
- ![alt text](image-708.png)
- Build and push an image of the client app to ACR 
- Use the following commands to build and push an image to ACR 
```shell 
az login 
az group create --name MyResourceGroup --location eastus
az acr create --resource-group MyResourceGroup --name MyContainerRegistry --sku Basic
az acr login --name MyContainerRegistry
docker build -t myimage:latest .
docker tag myimage:latest MyContainerRegistry.azurecr.io/myimage:latest
docker push MyContainerRegistry.azurecr.io/myimage:latest

# Verify the image 
az acr repository list --name MyContainerRegistry --output table

```
- Next, create a container app
- ![alt text](image-709.png)
- ![alt text](image-710.png)
- ![alt text](image-711.png)
- ![alt text](image-712.png)
- Now container app is deployed 
- ![alt text](image-713.png)
- To deploy a container app directly from source code without creating an image first, use this command: 
```shell 
az containerapp up -n worldtripinfo --environment worldtrip-environment --source . --registry-server nishantworldtrip.azurecr.io -g worldtrip-rg --registry-username=nishantworldtrip --registry-password=Ld3rVa++M9PKBRfCOFXrpt/5EPIW9RUouHe5rwqdmK+ACRBqcsF0
```
- We can modify the URL to fetch the trips from the azure container app we just deployed inside the index.html file 
- Now we need to create a new tag for this image and deploy it again 
- Inside the container app, we need to create a new revision which will use the updated image 
- ![alt text](image-714.png)
- ![alt text](image-715.png)
- ![alt text](image-716.png)
- Note the revision has its own URL
- ![alt text](image-717.png)
- ![alt text](image-718.png)
- The old revision is deactivated 
- ![alt text](image-719.png)

## Splitting Traffic with Revisions
- ![alt text](image-720.png)
- Activate the inactive revision with 50% traffic
- ![alt text](image-721.png)
- Now if we go to the main URL of the container app, open it and keep refreshing, we can see sometimes it will point to old revision and sometimes to new one 
- ![alt text](image-722.png)

## Deploy to Azure Container Apps with GitHub Actions
- Azure Container Apps allows you to use GitHub Actions to publish revisions to your container app. As commits are pushed to your GitHub repository, a workflow is triggered which updates the container image in the container registry. 
- Azure Container Apps creates a new revision based on the updated container image.
- The GitHub Actions workflow is triggered by commits to a specific branch in your repository.
-  When creating the workflow, you decide which branch triggers the workflow.
```yaml
 steps:

  - name: Log in to Azure
    uses: azure/login@v1
    with:
      creds: ${{ secrets.AZURE_CREDENTIALS }}

  - name: Build and deploy Container App
    uses: azure/container-apps-deploy-action@v1
    with:
      appSourcePath: ${{ github.workspace }}/src
      acrName: myregistry
      containerAppName: my-container-app
      resourceGroup: my-rg

```
- The action uses the Dockerfile in appSourcePath to build the container image. If no Dockerfile is found, the action attempts to build the container image from source code in appSourcePath.
```yaml 
 name: Azure Container Apps Deploy

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3

      - name: Log in to Azure
        uses: azure/login@v1
        with:
          creds: ${{ secrets.AZURE_CREDENTIALS }}

      - name: Build and deploy Container App
        uses: azure/container-apps-deploy-action@v1
        with:
          appSourcePath: ${{ github.workspace }}/src
          acrName: <ACR_NAME>
          containerAppName: my-container-app
          resourceGroup: my-container-app-rg

```

## Autoscaling Container Apps 
- Container apps can be scaled automatically 
- Scaling is always per revision 
- Scaling is done by adding or removing replicas for the revision 
- Ensures there is enough compute power to handle incoming traffic 
- Scaling can be configured based on various parameters 
- We can scale to zero - no cost. 

### Autoscaling Components
- ![alt text](image-723.png)
- Scaling Limits: Set the minimum and maximum number of replicas per revision 
- ![alt text](image-724.png)
- Scaling Rules: Define the trigger for scaling. 3 categories of triggers: 
- HTTP, TCP, Custom Triggers 
- ![alt text](image-725.png)
- Scaling Behavior: Combines limits and rules 
- Sets how rules are evaluated and how scale is executed i.e Polling interval, scale up steps etc. 
- Usually should not be modified 
- Can be done using the portal, CLI or ARM template 
- Adding scaling configuration creates a new revision 
- ![alt text](image-726.png)

## Scaling with KEDA 
- k8s event driven autoscaler 
- scales k8s deployments based on events collected from various event sources 
- Remember: Container apps are based on K8s 
- Not related to Azure, integrated into Container Apps 

## KEDA Concepts 
- Event Source: External source monitored by KEDA: Examples: Azure Storage Queue, ActiveMQ, Memory etc. 
- Provides metrics for KEDA to process 
- Metrics are sent to Scaler 
- Scalers: Component that receive metrics from event source 
- Then decides whether a deployment should be scaled 
- Currently there are more than 60 types of scalers 
- Scaled Object/Scaled Job: Specification for describing how KEDA should scale deployments and which trigger to use. 
- ![alt text](image-727.png)
- Note the event source is Kafka

## Using KEDA with Container Apps 
- KEDA scalers can be used in Container Apps 
- Using Custom scale rules 
- Specifications are entered as metadata fields 
- Authentication to resources is done using secrets 
- i.e Connection Strings 
- First create a storage account and create a storage queue inside it. This queue will act as the event source for KEDA 
-  Add a new secret to container app 
-  Copy the connection string for storage queue and add it as a secret in the container app 
-  ![alt text](image-728.png)
-  ![alt text](image-729.png)
-  This is based on KEDA trigger specification for CPU scaler: 
```yaml 
 triggers:
- type: cpu
  metricType: Utilization # Allowed types are 'Utilization' or 'AverageValue'
  metadata:
    type: Utilization # Deprecated in favor of trigger.metricType; allowed types are 'Utilization' or 'AverageValue'
    value: "60"
    containerName: "" # Optional. You can use this to target a specific container in a pod

```
- We will add the storage queue based custom scaler like this:
- ![alt text](image-735.png)
- This is based on the KEDA trigger specification for Azure storage queue scaler:
```yaml 
 triggers:
- type: azure-queue
  metadata:
    queueName: orders
    queueLength: '5'
    activationQueueLength: '50'
    connectionFromEnv: STORAGE_CONNECTIONSTRING_ENV_NAME
    accountName: storage-account-name
    cloud: AzureUSGovernmentCloud

```
- Now a new revision is deployed with 2 custom scale rules
- ![alt text](image-731.png)
- Now we go to the storage queue and add 6 messages in the queue. Note that when we add the 6th message, it will trigger KEDA queue scaler rule
- ![alt text](image-736.png) 
- Now we can see 2 replicas of the container app running 
- ![alt text](image-737.png)

## Service Connectors 
- It is often required to connect container apps to external services
- In containerized apps—like those running on Docker or Kubernetes—service connectors are tools or configs that link your app to external services: databases (PostgreSQL, MongoDB), message queues (RabbitMQ), cloud storage (AWS S3), or APIs. 
- Think of them as the plumbing—bridges that let containers, which are isolated by design, talk to the outside world securely and efficiently.
- ![alt text](image-738.png)
- Can be done in the regular way 
- Setting up manually the connection string 
- Defining authentication
- Setting up managed identity 
- And more. 
- However this is cumbersome and error prone. 
- Service connectors come to the rescue 
- We can use service connector to create a fully configured connection to other services 
- Add environment variables to the compute platform with all the necessary connection information 
- The code just needs to reference the env variable and use it to connect to the service 
- Service Connectors can be used from :
- ![alt text](image-739.png)
- ![alt text](image-740.png)
- We will use service connector in the pricing service 
- It will connect to Azure SQL to retrieve pricing information 
- Connection to Azure SQL will be done using Service Connector 
- We will first create a container app for worldtrip pricing project 
- We will setup a worldtripdb database which will contain the table for the Tripprices. 
- Our container app will connect to this database using service connectors 
- ![alt text](image-741.png)
- We can also validate the connection 
- ![alt text](image-742.png)
- Note it will add an environment variable AZURE_SQL_CONNECTIONSTRING
- ![alt text](image-743.png)
- Note that this environment variable takes it value from a secret 
- Go to secrets and view the azure sql connection string secret which is a connection string stored in a secret(which is more secure)
- ![alt text](image-744.png)
- Service connectors make it easy to connect to other Azure Services. 

## Developing Microservices with Dapr 
- Manages service to service communication 
- Provides additional services 
- It is technology, platform and cloud agnostic. 
- Can be used even if it used by a python based system 
- Created by Microsoft 
- Integrated into Container Apps 
- It is a type of a service mesh.  

## Problems solved by Service Mesh 
- Microservices communicate between them a lot 
- The communication cause a lot of problems and challenges:
- Timeouts 
- Security
- Retries 
- Monitoring 
- Lets assume a system with 4 services 
- ![alt text](image-745.png)
- In the above diagram, whether it is timeout, error or communication over TCP, if we try to handle all of these scenarios within the service code itself, it will become cumbersome. 
- Service Mesh is a collection of software components that sit near the service and manage all service-to-service communication. 
- Provides all communication services
- The service interacts with the service mesh only 

### Services provided by Service Mesh 
- Protocol conversion(can convert communication over RESTAPI to TCP )
- Communication Security using Encryption 
- Authentication using AD 
- Reliability(using timeouts, retries, health checks, circuit breaking)
- Monitoring 
- Service Discovery(provides loose coupling)
- Testing (A/B testing, traffic splitting)
- Load Balancing(routing the requests to different instances of the service)

### Circuit Breaker 
- Prevent cascading failures when service fails 
- ![alt text](image-746.png)
- ![alt text](image-747.png)

### In short, service's developers need not handle communication aspects when using Service Mesh 

## Service Mesh Architecture 
- We have Control Plane and Data Plane 
- ![alt text](image-748.png)
### Data Plane:
- Definition: The data plane is responsible for handling the actual traffic between services.
- Core Element: Sidecar Proxies
- A lightweight proxy (e.g., Envoy, Linkerd Proxy) is deployed alongside each service instance, typically as a separate container in a pod (in Kubernetes).
- The sidecar intercepts all inbound and outbound traffic to/from the service, managing communication without the service itself being aware of the mesh.
- Functions:
- Routing and load balancing
- Encryption (e.g., mTLS for secure communication)
- Retry logic, circuit breaking, and timeouts
- Traffic splitting (e.g., for canary deployments or A/B testing)
- Collecting telemetry data (metrics, logs, traces)

### Control Plane:
- Control Plane:
- Definition: The control plane is the management layer that configures and coordinates the behavior of the data plane proxies.
- Core Element: Centralized management software (e.g., Istio's istiod, Linkerd's control plane components).
- Functions:
- Defines and distributes policies and configurations to the sidecar proxies.
- Manages service discovery (e.g., integrating with Kubernetes' service registry).
- Handles security policies (e.g., issuing certificates for mTLS).
- Aggregates telemetry data from proxies for observability.
- Provides APIs or dashboards for administrators to define routing rules, policies, etc.

### How it works 
- Service Communication:
- Instead of services communicating directly with each other, all traffic is routed through the sidecar proxies.
- For example, Service A sends a request to Service B:
- Service A → Proxy A (outbound) → Proxy B (inbound) → Service B.
- The proxies handle the heavy lifting (e.g., retries, encryption, logging) transparently.
- Injection of Sidecars:
- In environments like Kubernetes, sidecar proxies are automatically injected into pods either manually or via an admission controller (e.g., Istio's sidecar injector).
- Control Plane Interaction:
- The control plane continuously communicates with the sidecar proxies to update configurations, enforce policies, and collect telemetry.

```text 
 +-------------------+       +-------------------+
| Service A         |       | Service B         |
|+-----------------+|       |+-----------------+|
|| App Container   ||       || App Container   ||
|+-----------------+|       |+-----------------+|
|| Sidecar Proxy   ||<----->|| Sidecar Proxy   ||  <- Data Plane
|+-----------------+|       |+-----------------+|
+-------------------+       +-------------------+
         ^                          ^
         |                          |
         +--------------------------+
                   Control Plane
         (Policy, Config, Telemetry)

```

## Types of Service Mesh 
- 2 main types 
- In Process 
- Sidecar 

### In Process 
- ![alt text](image-749.png)
- Code for the mesh runs in the same process as the services code 
- No inter process communication is required 

### Sidecar 
- Code for mesh is an out of service process component 
- Here service code makes a network call to the service mesh component 
- ![alt text](image-750.png)

### Comparison between them 
- In Process offers better performance as there are no network calls 
- Side car advantage is platform agnostic 
- Mesh code can be in Node.JS and services could be coded in .NET Core. 
- ![alt text](image-751.png)
- Always go for Sidecar 

## Dapr components 
- Add more capabilities to Dapr 
- In addition to Service Mesh capabilities 
- Represented as components 
- Each component is responsible for a specific capability 
- Capabilites are implemented using different underlying components 
- Can be switched without changing component spec. 
- ![alt text](image-752.png)
- We can switch from Dynamo DB to Cosmos DB 
- Nothing from the code point will change, we can just switch the implementation. 
- Think of it as MassTransit
- More like an abstraction 
- To implement components we need a component Schema 

### Component Schema 
- YAML file defining the component 
- Specifies the component type, authentication, metadata, scopes and more 
- ![alt text](image-753.png)


## Dapr in Container Apps 
- Deeply integrated into Container Apps 
- Different configuration between service invocation(Service Mesh) and components 
### Service Invocation
- Enabled on the container app 
- Almost no change in code 
- Allows tracing 
- Easy to configure 

### Dapr components 
- Defined on the Environment Scope 
- Attached to the relevant container apps 
- Have slightly leaner schema 
- ![alt text](image-754.png)
- Components can define scopes 
- Basically appId assigned to Container Apps 
- Only container app with appId defined as scope can use the component 
- Scope is optional though! 

## Connecting the WorldTripPricing to the WorldTripInfo 
- Look the following code: 
- Note we are making a call from TripInfo API to the Pricing API using HttpClient 
```c#
 using System.Runtime.CompilerServices;

var builder = WebApplication.CreateBuilder(args);

// Add services to the container.
// Learn more about configuring Swagger/OpenAPI at https://aka.ms/aspnetcore/swashbuckle
builder.Services.AddEndpointsApiExplorer();
builder.Services.AddSwaggerGen();
builder.Services.AddCors();

var app = builder.Build();

// Configure the HTTP request pipeline.
if (app.Environment.IsDevelopment())
{
    app.UseSwagger();
    app.UseSwaggerUI();
    app.UseCors(builder=>builder.WithOrigins("*"));
}

app.UseHttpsRedirection();

var baseURL = (Environment.GetEnvironmentVariable("PRICING_API_URL") ?? "https://localhost:5002") + "/tripPricing/";

var client = new HttpClient();
// Adding app id as part of the header
client.DefaultRequestHeaders.Add("dapr-app-id", "world-trip-pricing");


app.MapGet("/tripInfo", async () =>
{
    var tripList = new List<TripInfo>
        {
            new(1, "Paris", "paris.jpg", GetTripPricing(1)),
            new(2, "New York", "newyork.jpg", GetTripPricing(2)),
            new(3, "Tokyo", "tokyo.jpg", GetTripPricing(3))           
        };
    return tripList;
})
.WithName("GetTripInfo")
.WithOpenApi();

app.Run();

decimal GetTripPricing(int tripId)  {

    var tripPricing=client.GetAsync(baseURL + tripId).Result.Content.ReadFromJsonAsync<TripPricing>().Result;
    return tripPricing.Price;
    

}
record TripInfo(int TripId,String Location, String PhotoUrl, decimal Price);

record TripPricing(int TripId,decimal Price);


```
- Then we will deploy a new revision of the WorldTripInfo Container App with the updated code as above. 
- If we try to run this code, it will not work as it will not find the Pricing_Api_Url. 
- To fix this we will create another revision and define the environment variable for Pricing_Api_Url as below 
- ![alt text](image-755.png)
- Now it will work and WorldTripInfo container app will fetch the details from the WorldTripPricing Container app. 
- But is it the best practice ?
- Lets use Dapr here 
- ![alt text](image-756.png)
- ![alt text](image-757.png)
- ![alt text](image-758.png)
- Similar to worldtripInfo, we will also enable dapr for worldtrip pricing app 
- ![alt text](image-759.png)
- Remember in the above code we set the dapr-app-id to world-trip-pricing 
- This will allow worldtripinfo dapr sidecar to discover and find the dapr sidecar for world-trip-pricing app. 
- This will help them to connect. 
- Dapr is installed as a sidecar and is available at localhost:3500 port 
- ![alt text](image-760.png)
- When we use dapr it will look at the dapr-app-id in the header and redirect and get info from the world-trip-pricing dapr sidecar. 
- ![alt text](image-761.png)


## Container App Jobs 
- So far we have worked with web apps and API 
- For this we used regular container apps 
- These container apps listen to incoming requests and are always running. 
- Container apps also support jobs 
- Run for finite time and exit 
- Also called Container App Jobs 
- Great for data processing, machine learning, reporting and more. 

### Job Triggers 
- Container App jobs are triggered using the following trigger types 
- ![alt text](image-762.png)
### Cron Expressions 
- Widely used to schedule operations 
- Format can vary between vendors 
- Specify the minute, hour, day of the month, month and day of the week 
- Each element is indicated as a *(always), number, expression. 
- Spaces between the elements 
- 0 0 * * * (Every day at 00:00)
- */5 * * * * (Every 5 minutes)
- 0 * 4 * *  (At the beginning of every hour on the 4th day of the month)
- 30 5 * * 1 (Every Monday at 5.30 AM)

### Deploying Container App Jobs 
- Shared same environment with the regular container apps 
- Use the same network and logging 
- Deployment is similar to regular container apps 

### Limitations to Container App Jobs 
- No revisions 
- No Dapr support (communication with other container apps or APIs has to be direct URL based)
- No ingress configuration (Remember, jobs donot receive incoming traffic)

## Using Azure Container App Jobs 
- We have the following code running inside a console application 
```c#
 // See https://aka.ms/new-console-template for more information
var destinations = new List<String> { "Paris", "New York", "Tokyo" };
var trending = new Random().Next(0, 3);
Console.WriteLine($"Trending destination: {destinations[trending]}");
```
- Note that this is a console application not a web app. 
- We will build and push an image of this code to the Azure Container Registry 
- ![alt text](image-763.png)
- Now we will deploy this code as a Container App Job 
- ![alt text](image-764.png)
- We will run this job every minute 
- ![alt text](image-765.png)
- ![alt text](image-766.png)
- ![alt text](image-767.png)
- We can see in the console logs that the job ran successfully 
- ![alt text](image-768.png)


## Securing Container Apps
- Container Apps offer various mechanisms to improve security 
- Same mechanisms found in other services
- Improve network and access security 
### Ingress
- Controls incoming traffic to the container app 
- By default allows external traffic with no limitations 
- Can be set to allow only internal traffic i.e  between other container apps in the same environment 
- For .e.g TripPricing API and TripInfo API can be allowed to communicate only with themselves in the same environment 
- Great for services that should be called only from other services 
- Can allow only specific IP addresses to access the service 
- Similar to Access Restrictions in App Service  
- Current we accept traffic from anywhere 
- ![alt text](image-769.png)
- We can change Ingress Traffic to container app environment 
- ![alt text](image-770.png)
- Note the URL has changed and it has internal inside it  
- https://worldtrippricing.internal.wonderfulisland-12425134.westus2.azurecontainerapps.io

### Authentication 
- Authentication can be added to the container app 
- Requires user authentication in order to access the app 
- Support multiple identity providers 
- Similar to authentication in App Services 
- ![alt text](image-771.png)
- ![alt text](image-772.png)
- ![alt text](image-773.png)
- ![alt text](image-774.png)
- Now after adding the identity provider, we try to access the container app again, we are redirected to the sign-in page 
- ![alt text](image-775.png)

### Managed Identity 
- Container Apps can have their own managed identity 
- Can be used when accessing other resources such as database, keyvaults and more 
- Used exactly the same as with other services 
- ![alt text](image-776.png)
- ![alt text](image-777.png)

### Additional Security Controls 
- Add Application Gateway + WAF in front of the Container App 
- Use Existing Vnet, configure NSGs 
- Store secrets in the Container App's secrets and not in code. 

## Resiliency 
- Various mechanisms are there in container app to remain available in case of regional failure, shutdown etc 
- We can handle both error and zonal failures 
- Container Apps can be deployed in multiple zones in a region to improve reliability
- Replicas are distributed across the zones in the region 
- Internal load balanver distributes traffic between zones 
- When a zone goes down, replicas in other zones continue working 
- Effective when there are more than 1 replica 
- They also affect the cost(goes up !)
- Availability Zones are configured on Environment level 
- Cannot be changed once environment is deployed 
- Requires a special Vnet.  
- When we create a new container app, create a new environment 
- ![alt text](image-778.png)
- ![alt text](image-779.png)
- Note that we deploy it across zones, a new Vnet is created with a new subnet(to communicate between zones) to manage synchronization between replicas across various zones
  
### Resiliency Policies 
- Define behaviours of service-to-service communication 
- Will not work when Dapr is enabled(coz Dapr takes care of everything)
- Define timeouts, retries and more 
- Easy to configure 
- Per container app 
- ![alt text](image-780.png)
- ![alt text](image-781.png)
- ![alt text](image-782.png)
- ![alt text](image-783.png)

### Dapr Resiliency Policies
- Dapr has its own resiliency policies for service invocations
- Cannot be configured in Container Apps 
- These are baked into Dapr in Container App 
- ![alt text](image-784.png)

### Implementing DR 
- Disaster recovery plan helps with a complete region shutdown
- If our system needs to work in this scenario, a DR plan must be made 
- Container apps is a regional service 
- If region goes down, the container app also goes down 
- So we can implement DR in Container App like this 
- ![alt text](image-785.png)
- ![alt text](image-786.png)
- This will however double the cost of single deployment + Front Door cost(which is expensive)


## Logging and Monitoring of Container Apps 
- Container Apps have lot of moving parts such as revisions, replicas, code, containers and more.
- We want to know how these parts are behaving 
- Figure out if there is going to be a problem 
- Report a problem 
- Analyze Trends 
- Logging and Monitoring help with that 
- Based on Logs and Metrics in Azure 
- Holds a lot of data about Container Apps status 
- Allows setting alerts 
- ![alt text](image-787.png)
- ![alt text](image-788.png)
- ![alt text](image-790.png)
- ![alt text](image-791.png)
- ![alt text](image-792.png)
- ![alt text](image-793.png)
- ![alt text](image-794.png)
- ![alt text](image-795.png)
- ![alt text](image-796.png)
- ![alt text](image-797.png)


## Architecting Apps for Azure 
- Architecting for the cloud is different than classic Software Architecture
- Two main differences:
- Use existing services
- ![alt text](image-798.png)
- Consider cost 
- ![alt text](image-799.png)

## Choosing the Compute Platform 
- ![alt text](image-800.png)

## Choosing the Data Platform 
- ![alt text](image-801.png)
- Azure SQL offers best SLA and best availability

## Choosing the Messaging Platform 
- ![alt text](image-802.png)

## Implementing Security 
- Restrict access to VMs and App Services
- Use NSG 
- Use encryption in data stores 
- Use strong authentication

## Implementing Logging and Monitoring
- Utilize Alerts 
- Use Application Insights, Azure Monitor, Log Analytics Workspace 
- Create dashboards to visualize the system state 
- Use application insights to gain insights into your app 

## Azure Architecture Center 
- Central hub for all things Azure architecture 
- ![alt text](image-803.png)
- ![alt text](image-804.png)

## Case Studies
- ![alt text](image-805.png)

## Dunderly (Paper Source)
- Sells Paper Supplies
- ![alt text](image-806.png)
### Requirements 
- Functional and Non-Functional Requirements 
- ![alt text](image-807.png)
- ![alt text](image-808.png)
- ![alt text](image-810.png)
- ![alt text](image-811.png)

### Figure out the Data Volume 
- ![alt text](image-812.png)
- ![alt text](image-813.png)

### Final Set of Requirements 
- ![alt text](image-814.png)

### Mapping the Components
- We want to map one service to one entity 
- ![alt text](image-815.png)
### Messaging between Components
- For Logging, we will use a Queue because it supports fire and forget mechanism.
- Logging service pulls log records from queue and processes them 
- ![alt text](image-816.png)

### Logging Service 
- Very important for a system with lot of services 
- ![alt text](image-817.png)
- Logging in Azure is implemented with 
- Azure Log Analytics(Part of Azure Monitor and offers great integration with other services)
- Handles huge amount of data 
- Offers query language for analysis 
- Can be streamed to log analytics tools like Power BI 
- ![alt text](image-818.png)
- Log analytics looks like this with KQL
- ![alt text](image-819.png)
- Cost of Log Analytics per month 
- ![alt text](image-820.png)

### View Service 
- ![alt text](image-821.png)
- This is a web app 
- In this service we only have User Interface 
- ![alt text](image-822.png)
- Static websites can be implemented in Azure using either App Service or Static Web Apps 
- ![alt text](image-823.png)
- Monthly cost of App Service 
- ![alt text](image-824.png)
- Cost of Static Web App 
- ![alt text](image-825.png)
- Clearly Static Web Apps are more cost effective. 
- Remember we dont need autoscaling and we dont have lot of concurrent users. 

### Employees Service 
- Allows end users to query employee's data 
- Allows us to perform actions on data 
- It doesnot allow us to display the data. Only CUD (Create, Update, Delete)
- This will be a WebAPI 
- We can use .NET Core. 
- In Azure a webapi can be exposed either by App Service or Azure Function Apps 
- ![alt text](image-827.png)
- ![alt text](image-828.png)
- We can go with App Services 
- Cost of the App Service 
- ![alt text](image-829.png)
- Choosing a database 
- ![alt text](image-830.png)
- ![alt text](image-831.png)
- ![alt text](image-832.png)
- Architecture of this service 
- ![alt text](image-833.png)
- API should allow us to get full employee details by Id, List of employees by parameters 
- Add Employee 
- Update employee details 
- Remove employee(soft delete only)
- Add document 
- Remove document 
- Get document 
- Search documents by parameters 
- Do we need a separate Document Handler service? Since only Employee entity requires documents, so no. 
- API should look like this 
- ![alt text](image-834.png)
- ![alt text](image-835.png)
- Employee Service redundancy: we will use autoscale capability of App Services 
- ![alt text](image-836.png)


### Salary Service 
- ![alt text](image-837.png)
- This is a WebApi built using .NET Core
- We can choose between App Service or Function Apps 
- ![alt text](image-838.png)
- Go with App Services here 
- Classic 3 layer architecture 
- API would do the following: 
- Add Salary Requests 
- Remove salary request 
- Get salary request 
- Approve salary request 
- Reject salary request 
- ![alt text](image-839.png)
- Salary Service redundancy: we will use autoscale capability of App Services 


### Vacation Service 
- Allows employees to manage their vacation days 
- Allows HR to set available vacation days for employees 
- This is again a Web Api built using .NET Core 
- This will again be an App Service with similar costs and autoscale capabilities.
- ![alt text](image-840.png)
- ![alt text](image-841.png)


### Payment Interface 
- ![alt text](image-842.png)
- This inteface is basically a Service or Batch process running on a schedule
- It will be built using .NET Core. 
- We can choose between App Service WebJob and Function Apps 
- ![alt text](image-843.png)
- ![alt text](image-844.png)
- Export of data can take lot of time. 
- So we will go with App Service WebJobs 
- ![alt text](image-846.png)
- There is no redundancy for web jobs 
- We need to manually add monitoring for catching failures 
- ![alt text](image-847.png)
- Architecture so far 
- ![alt text](image-848.png)

### Security
- Data Encryption 
- Network Security 
- Access Restrictions 
- ![alt text](image-849.png)
- ![alt text](image-850.png)
- ![alt text](image-851.png)
- We need to add Application Gateway with WAF 
- ![alt text](image-852.png)
- This is expensive however. 
- ![alt text](image-853.png)
- Access Restrictions: Access to resources should be limited to allowed resources only. 
- ![alt text](image-855.png)
- Restrict access to App Service 
- Add NSG rule to allow traffic from the App GW's Vnet 
- ![alt text](image-856.png)
- ![alt text](image-857.png)
- Restrict access to Azure SQL 
- Get outbound IP of the App Service 
- Add firewall rule to the Azure Sql 
- ![alt text](image-858.png)
- ![alt text](image-859.png)
- Restrict access to Storage Account 
- ![alt text](image-860.png)
- ![alt text](image-861.png)
- Why cant we use Managed Identity or User Assigned Managed Identity in this case. 

### Final Architecture 
- ![alt text](image-862.png)
- Total cost per month is 
- ![alt text](image-863.png)
- ![alt text](image-864.png)


## Case Study #2 
- Deals with Autonomous Cars 
- ![alt text](image-866.png)

### Requirements 
- ![alt text](image-867.png)
- ![alt text](image-868.png)

### Questions we should ask the Customer
- ![alt text](image-869.png)
- ![alt text](image-870.png)

### Calculating the Data Volume 
- ![alt text](image-871.png)
- We also need to consider the Retention Period
- Also what happens to the data after retention period 
- ![alt text](image-872.png)
- Why we need retention period ?
- ![alt text](image-873.png)
- We need 2 types of data: 
- ![alt text](image-874.png)
- ![alt text](image-875.png)
- If operational data is 1 week then 
- ![alt text](image-876.png)
- Max 4TB a week which we can store. 
- ![alt text](image-877.png)

### Mapping the Components
- ![alt text](image-879.png)
- We want to store aggregated data in a different data store: so we will store it in Data Warehouse 
- Since retention period is 1 week, we will move data to Archive Db. 
- We also need to figure out how the components will talk to each other. We will use TCP/IP protocol. Most IoT devices work with TCP/IP protocol as HTTP protocol is too verbose. 
- When we move from OperationalDB to ArchiveDB , we will use ETL process
- Remember for ETL we used to use Azure Data Factory. 
- Azure's primary service for ETL is Azure Data Factory (ADF), a fully managed, cloud-based data integration platform. ADF enables you to create, schedule, and orchestrate ETL and ELT (Extract, Load, Transform) pipelines without needing to manage underlying infrastructure. 
- It's not a BI tool itself but serves as the backbone for moving and transforming data, which can then feed into BI solutions like Power BI for analysis and visualization.
- Key Features:
- Connectors: Over 90 built-in, maintenance-free connectors for sources like SQL Server, Salesforce, SAP, and Amazon S3.
- Data Flows: Code-free transformation with Mapping Data Flows, powered by Apache Spark, for scalable data processing.
- Scalability: Serverless architecture that scales dynamically based on workload.
- Integration: Works seamlessly with other Azure services, including Power BI, for downstream BI tasks.
- ![alt text](image-880.png)

### Telemetry Gateway 
- Receives Telemetry data from cars using TCP 
- Pushes the telemtry data to pipeline for further processing
- It can either be a console app or service. 
- It must handle huge load like 7000 msgs/sec 
- Must offer great performance 
- ![alt text](image-881.png)
- We can go with Node.JS 
- ![alt text](image-882.png)
- Listeners in Azure for this kind of problem: 
- ![alt text](image-883.png)
- We can use a VM 
- ![alt text](image-884.png)
- However we have a problem with scaling. Scaling VMs is hard. 
- So we can utilize VM Scalesets and Load Balancer. 
- ![alt text](image-885.png)
- ![alt text](image-886.png)
- ![alt text](image-887.png)
- In our case we only need service interface. 
- Therefore Telemetry Gateway will be implemented with Load Balancer and VM Scale Sets. 

### Telemetry Pipeline 
- Gets the telemetry messages from the gateway 
- Queues the telemetry for further processing 
- Basically - a queue for streaming high volume data 
- Remember this diagram 
- ![alt text](image-889.png)
- Event Hubs are designed for heavy loads 
- ![alt text](image-890.png)
- We will go with 7 throughput units(TUs). Each TU supports upto 1000 messages/second (and we will recieve 7000 messages/sec)


### Telemetry Processor 
- It receives messages from the pipeline
- Processes the messages(mainly validation)
- Stores the messages in a data store 
- We need to determine the Azure service for both the processor and data store 
- For Processing the messages, we can go with Azure Function Apps
- ![alt text](image-891.png)
- Cost would be very less 
- ![alt text](image-892.png)
- For data store we are looking for 
- ![alt text](image-893.png)
- We can go with Cosmos DB 
- ![alt text](image-894.png)
- Cosmos DB is quite costly 
- ![alt text](image-895.png)
- Event Hubs will automatically balance the load so we dont need 7000 RU/s 
- ![alt text](image-896.png)
- For the archive database we need to support huge amount of data 
- ![alt text](image-897.png)
- We can use Storage Account here and we can use Archive tier. 
- ![alt text](image-898.png)
- Pricing will look like this 
- ![alt text](image-899.png)

### Telemetry Viewer 
- It allows end users to query telemetry data 
- Displays real time data 
- However, it doesnot analyze the data 
- It will be Web App and Web Api 
- We need backend and frontend 
- For backend we will go with node.js and for front end we will go with React.js 
- We can use App Service here for both 
- ![alt text](image-900.png)
- Cost is nominal 
- ![alt text](image-901.png)
- ![alt text](image-902.png)
- API use cases are as follows: 
- ![alt text](image-903.png)
- ![alt text](image-904.png)
- Redundancy is based on auto scaling feature of App Service. 

### BI Application 
- We want this application to analyze telemetry data and display custom reports about the data, trends, forecast etc. 
- For e.g we want to know how many cars did break during the last month? 
- What is the total distance the cars drove ?
- BI Application is ALWAYS based on an existing tools 
- Lot of BI tools out there 
- ![alt text](image-905.png)
- Designing BI solution is not part of architect's job, use a BI expert 
- In Azure we have Power BI integration through Azure Synapse Analytics, Azure Data Lake Storage, Azure Cosmos DB, Azure SQL database. 

### Security 
- Pay attention to public accessible databases and unprotected access to App Service 
- We need to block access to databases from unauthorized IP addresses 
- Client can decide not to place WAF in front of App Service since it is a small service and offers only read-only operations and we want to save costs 


### Final Architecture 
- ![alt text](image-906.png)
- Final cost 
- ![alt text](image-907.png)
- ![alt text](image-908.png)


## Case Study 3
- Grocecoll --> Grocery collection service 
- ![alt text](image-909.png)
- ![alt text](image-910.png)
- ![alt text](image-911.png)
- ![alt text](image-912.png)
- ![alt text](image-913.png)

### Data Volume 
- 1 List = 500Kb 
- 10000 lists /day = 5GB /day => 2TB /year 
- ![alt text](image-914.png)

### Mapping the Components 
- ![alt text](image-915.png)

### Messaging between the Components 
- ![alt text](image-916.png)

### Lists Receiver 
- ![alt text](image-917.png)
- Either a console or service 
- Receiver code can be a Function App 
- ![alt text](image-918.png)
- ![alt text](image-919.png)
- We can use Azure MySql Database 
- ![alt text](image-920.png)
- ![alt text](image-921.png)
- ![alt text](image-922.png)

### Lists Service 
- ![alt text](image-923.png)
- We can make it a web app that calls a webapi
- We can go for App Service 
- ![alt text](image-924.png)
- We will implement 3 layer architecture 
- ![alt text](image-925.png)
- ![alt text](image-926.png)
- ![alt text](image-927.png)

### FrontEnd 
- ![alt text](image-928.png)
- We need to decide between Desktop WPF app or Web based(Electron or React Native)
- ![alt text](image-929.png)
- We can go for React Native 

### Export Lists Data
- ![alt text](image-930.png)
- ![alt text](image-931.png)

### Security 
- Block access to database from unauthorized IP Addresses 
- Here App Service is a small service with read only operations and we need to save costs 

### Final Architecture 
- ![alt text](image-932.png)
- ![alt text](image-933.png)

## Case Study #4 
- PayRawl System 
- ![alt text](image-934.png)

### Requirements 
- ![alt text](image-935.png)
- ![alt text](image-936.png)
- ![alt text](image-937.png)
- ![alt text](image-938.png)
- ![alt text](image-939.png)

### Mapping the Components 
- ![alt text](image-942.png)
- Messaging between components is queue based 

### File Handler
- ![alt text](image-943.png)
- It is either a console or a service 
- We can go for Function Apps 
- ![alt text](image-944.png)
- Cost is 0 in the consumption tier: we have only 15000 executions per month 
- ![alt text](image-945.png)
- ![alt text](image-946.png)
- We can go for .NET Core as its performance is better and .NET Core offers threading support also 


### Queue 
- ![alt text](image-947.png)
- ![alt text](image-948.png)
- We can go for Event Hubs 
- ![alt text](image-949.png)
- We just need 1 TU 
- ![alt text](image-950.png)

### File Formatter 
- ![alt text](image-951.png)
- Application will either be a console or a service 
- We can again use Function Apps 
- ![alt text](image-952.png)
- Cost is 0 
- ![alt text](image-953.png)

### File Calculation Service 
- ![alt text](image-954.png)
- Similar to File Formatter so we can also use Azure Function apps and it will cost us 0 

### File Exporter 
- ![alt text](image-955.png)
- Similar to File Calculation Service and we will use Azure Function Apps and it will cost us 0 

### Logging Service 
- ![alt text](image-956.png)
- We can go for Azure log analytics 
- ![alt text](image-957.png)
- ![alt text](image-958.png)
- Max retention period for Log Analytics is 2 years. 


### Security 
- System is internal only, so no substantial security risks 
- We need to make sure data is encrypted and validated 
- ![alt text](image-959.png)

### Final Architecture 
- ![alt text](image-960.png)
- ![alt text](image-961.png)

## Migrating to the Cloud 
- ![alt text](image-962.png)
- ![alt text](image-963.png)

### Motivation Assessment 
- Why we want to move to the cloud?
- To save costs (Not always the case, sometimes cloud systems can cost more than on-premises, need to do thorough cost estimation)
- To take advantantage of cloud capabilities(scalability, redundancy)-->But we need to make sure migrated system can use cloud capabilities
Example: Legacy single session app that cannot be scaled will end up on a single VM just like on-prem 

### Migration Strategies 
- Lift and Shift (quickest but least efficient one)
- ![alt text](image-965.png)
- Refactoring 
- ![alt text](image-966.png)
- Rewrite (slowest but takes full advantage of all cloud services)
- ![alt text](image-967.png)
- ![alt text](image-964.png)
- Comparison of cloud migration strategies 
- ![alt text](image-968.png)
- These migrations are often combined 
- First do lift and shift and then start optimization. Some applications may be refactored and others may require rewriting as well. 


### System Assessment 
- We need to ask the right questions: 
- ![alt text](image-969.png)
- Answers dictate the migration strategy 
- ![alt text](image-970.png)
- ![alt text](image-971.png)
- ![alt text](image-972.png)
- We need to know a tool called **Azure Migrate** 
- It is a central hub for assessing and migrating various resources 
- It uses platform specific agents to discover the resources that can be migrated 
- Provides migration recommendations 
- It is free. 
- ![alt text](image-973.png)
- ![alt text](image-974.png)

### Migration 
- Time for the actual migration 
- Lift and shift is the easiest strategy 
- ![alt text](image-975.png)
- Next is Refactor 
- ![alt text](image-976.png)
- Finally we have rewrite 
- ![alt text](image-977.png)
- For DB Migration, prefer managed version of the DB and not a VM  
- Migration itself is better than DB's own tools and not via Azure migration services 

### App Enhancements
- Not necessarily code changes 
- Main areas for improvements: 
- Logging and Monitoring using Azure Monitor 
- Network Protection using Application Gateway 
- ![alt text](image-978.png)

### Testing 
- Testing in cloud is similar to on-prem 
- Put strong emphasis on logging and monitoring 
- Make sure you have access to system's data 
- If system is auto-scaled or DRed- test these scenarios 
- Check performance- might vary from the on-prem figures 
- System might be slower in cloud compared to on-prem and opposite is also possible. 

### Go Live 
- Keep on eye on the costs 
- Setup budget alerts 
- Define tags for the various cloud services 
- Look at the data atleast once a month  
