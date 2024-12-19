## Topic One - Azure Core

**Azure Arc** can help manage your cloud environment

## How to work in Sandbox

    1. Powershell
    2.Bash CLI
    3.Use Azure CLI interactive mode

## TWO IMPORTANT PILLAR

    Physical Infrastructure pillar and Management Infrastructure pillar

## Physical Infrastructure Pillar
1.The physical infrastructure for Azure starts with datacenters.

2.Datacenters are grouped into **Azure Regions** or **Azure Availability Zones** that are designed to help you 

#### Regions
Places where atleast one or more data centers is(are) present.each region ensures that workloads are appropriately balanced.

#### Availability Zones.
these are datacenters within *azure region*.If one zone goes down, the other continues working.

**Use of avialablity zone** 

Azure can help make your app highly available through availability zones.
You can use availability zones to run mission-critical applications and build high-availability into your application architecture by co-locating your compute, storage, networking, and data resources within an availability zone. It cost extra to duplicate data in cloud (so that it can available whenever required).

Azure services that support availability zones fall into three categories:

1.Zonal services: You pin the resource to a specific zone (eg:, VMs, managed disks, IP addresses).

2.Zone-redundant services: The platform replicates automatically across zones (eg:zone-redundant storage,SQL Database).

3.Non-regional services: Services are always available from Azure geographies and are resilient to zone-wide outages as well as region-wide outages.

### Region Pairs
Most Azure regions are paired with another region within the same geography (such as US, Europe, or Asia) at least 300 miles away.For example, if a region in a pair was affected by a natural disaster, services would automatically fail over to the other region in its region pair.

### Sovereign Pairs
Sovereign regions are instances of Azure that are isolated from the main instance of Azure. You may need to use a sovereign region for compliance or legal purposes.

## Management Infrastructure
The management infrastructure includes Azure resources and resource groups, subscriptions, and accounts.

 1. **subscriptions** are a unit of management, billing, and scale. Similar to how resource groups are a way to logically organize resources.

 2. A subscription provides you with authenticated and authorized access to Azure products and services

 3. Azure subscription is linked to azure account using (Microsoft Entra ID or in a directory that Microsoft Entra ID trusts)

 An account can have multiple subscriptions, but it’s only required to have one. In a multi-subscription account, you can use the subscriptions to configure different billing models and apply different access-management policies.

 **Billing boundary** : This subscription type determines how an Azure account is billed.

 **Access control boundary** : This billing model allows you to manage and control access to the resources that users provision with specific subscriptions.

 ### Create additional Azure subscriptions
Create additional subscriptions for resource or billing management purposes.

**Environments**: You can choose to create subscriptions to set up separate environments for development and testing, security, or to isolate data for compliance reasons.

**Organizational structures**: You can create subscriptions to reflect different organizational structures. For example, you could limit one team to lower-cost resources, while allowing the IT department a full range.

**Billing**: You can create additional subscriptions for billing purposes.you might want to create one subscription for your production workloads and another subscription for your development and testing workloads.


### Management Group
Resources are gathered into resource groups, and resource groups are gathered into subscriptions.You organize subscriptions into containers called management groups and apply governance conditions to the management groups. All subscriptions within a management group automatically inherit the conditions applied to the management group.


# Topic 2 - Services provided by Azure


## Azure Virtual Machine
With Azure Virtual Machines (VMs), you can create and use VMs in the cloud.Just like a physical computer, you can customize all of the software running on your VM.VM provides (IAAS features).

You can run single VMs for testing, development, or minor tasks. Or you can group VMs together to provide high availability, scalability, and redundancy. Azure can also manage the grouping of VMs for you with features such as *scale sets* and *availability sets*.

### Scale set
Virtual machine scale sets let you create and manage a group of identical, load-balanced VMs.with virtual machine scale sets, Azure automates most of that work. Scale sets allow you to centrally manage, configure, and update a large number of VMs in minutes

### Availability sets
Availability sets are designed to ensure that VMs stagger updates and have varied power and network connectivity, preventing you from losing all your VMs with a single network or power failure.

Availability accomplish these objectives by grouping VMs in two ways: 
         update domain and fault domain.

**Update Domain**:This setup allows you to apply updates while knowing that only one update domain grouping is offline at a time.

**Fault domain**:an availability set splits your VMs across up to three fault domains. This helps protect against a physical power or networking failure by having VMs in different fault domains.

Some common examples or use cases for virtual machines include:
            During testing and development.
            When running applications in the cloud
            When extending your datacenter to the cloud
            During disaster recovery
        
### Azure virtual desktop  
Azure Virtual Desktop is a desktop and application virtualization service that runs on the cloud. It enables you to use a cloud-hosted version of Windows from any location.

**Enhance security**: With Azure Virtual Desktop, the data and apps are separated from the local hardware. The actual desktop and apps are running in the cloud, meaning the risk of confidential data being left on a personal device is reduced.

**Multi session windows**
Azure Virtual Desktop also provides a more consistent experience with broader application support compared to Windows Server-based operating systems.

**NOTE**
While virtual machines are an excellent way to reduce costs versus the investments that are necessary for physical hardware, they're still limited to a single operating system per virtual machine.

### Azure Containers
If you want to run multiple instances of an application on a single host machine, containers are an excellent choice.

**What are containers?** ->Containers are a virtualization environment. Much like running multiple virtual machines on a single physical host, you can run multiple containers on a single physical or virtual host.Containers are lightweight and designed to be created, scaled out, and stopped dynamically.ontainers are designed to allow you to respond to changes on demand. With containers, you can quickly restart if there's a crash or hardware interruption.
Example of Container is *Docker*.

#### Azure Container Instance
Azure Container Instances offer the fastest and simplest way to run a container in Azure.these are based on (PAAS).Azure Container Instances allow you to upload your containers and then the service runs the containers for you.

#### Azure Container Apps
Azure Container Apps are similar to container instance. Container Apps have extra benefits such as the ability to incorporate load balancing and scaling.

#### Azure Kubernetes Service
Azure Kubernetes Service (AKS) is a container orchestration service. An orchestration service manages the lifecycle of containers. When you're deploying a fleet of containers, AKS can make fleet management simpler and more efficient.

#### Using containers in your solution
you might split a website into a container hosting your front end, another hosting your back end, and a third for storage. This split allows you to separate portions of your app into logical sections that can be maintained, scaled, or updated independently.

#### Azure function
Azure Functions is an event-driven, serverless compute option that doesn’t require maintaining virtual machines or containers. If you build an app using VMs or containers, those resources have to be “running” in order for your app to function.

#### Benefits of Azure Functions
Using Azure Functions is ideal when you're only concerned about the code running your service and not about the underlying platform or infrastructure. 

Functions are commonly used when you need to perform work in response to an event (often via a REST request), timer, or message from another Azure service, and when that work can be completed quickly, within seconds or less.

Functions scale automatically based on demand.

Azure Functions runs your code when it triggers and automatically deallocates resources when the function is finished.

Functions can be either stateless or stateful. When they're stateless (the default), they behave as if they restart every time they respond to an event. When they're stateful (called Durable Functions), a context is passed through the function to track prior activity.

Functions are a key component of serverless computing. They're also a general compute platform for running any type of code. This flexibility allows you to manage scaling, run on virtual networks, and even completely isolate the functions.

#### Describe application hosting options
 Both VMs and containers provide excellent hosting solutions. VMs give you maximum control of the hosting environment and let u to configure it exactly how you want. Containers, with the ability to isolate and individually manage different aspects of the hosting solution, can also be a robust and compelling option.

### Azure App Service

App Service enables you to build and host web apps, background jobs, mobile back-ends, and RESTful APIs in the programming language of your choice without managing infrastructure. It offers automatic scaling and high availability.

Azure App Service lets you focus on building and maintaining your app, and Azure focuses on keeping the environment up and running.

#### Types of app services
1. **Web apps**
App Service includes full support for hosting web apps by using ASP.NET, ASP.NET Core, Java, Ruby, Node.js, PHP, or Python. You can choose either Windows or Linux as the host operating system.

2  **API apps**
Much like hosting a website, you can build REST-based web APIs by using your choice of language and framework. You get full Swagger support and the ability to package and publish your API in Azure Marketplace.

3  **WebJobs**

You can use the WebJobs feature to run a program (.exe, Java, PHP, Python, or Node.js) or script (.cmd, .bat, PowerShell, or Bash) in the same context as a web app, API app, or mobile app. WebJobs are often used to run background tasks as part of your application logic.

4  **Mobile apps**
Use the Mobile Apps feature of App Service to quickly build a back end for iOS and Android apps.

### Describe Azure virtual networking
Azure virtual networks and virtual subnets enable Azure resources, such as VMs, web apps, and databases, to communicate with each other, with users on the internet, and with your on-premises client computers.

**Azure virtual networks provide the following key networking capabilities:**

*Isolation and segmentation*
Azure virtual network allows you to create multiple isolated virtual networks. When you set up a virtual network, you define a private IP address space by using either public or private IP address ranges. The IP range only exists within the virtual network and isn't internet routable. 

*Internet communications*
You can enable incoming connections from the internet by assigning a public IP address to an Azure resource, or putting the resource behind a public load balancer.

*Communicate between Azure resources*
You want to enable Azure resources to communicate securely with each other.

1. Virtual networks can connect not only VMs but other Azure resources.such as the App Service Environment for Power Apps, Azure Kubernetes Service, and Azure virtual machine scale sets.

2. Service endpoints can connect to other Azure resource types, such as Azure SQL databases and storage accounts.

*Communicate with on-premises resources*
Azure virtual networks enable you to link resources together in your on-premises environment and within your Azure subscription.There are three mechanisms for you to achieve this connectivity:

1. Point-to-site virtual private network connections are from a computer outside your organization back into your corporate network. In this the client computer initiates an encrypted VPN connection to connect to the Azure virtual network.

2. Site-to-site virtual private networks link your on-premises VPN device or gateway to the Azure VPN gateway in a virtual network. In effect, the devices in Azure can appear as being on the local network. The connection is encrypted and works over the internet.

3. Azure ExpressRoute provides a dedicated private connectivity to Azure that doesn't travel over the internet. ExpressRoute is useful for environments where you need greater bandwidth and even higher levels of security.

*Route network traffic*
By default, Azure routes traffic between subnets on any connected virtual networks, on-premises networks, and the internet.

1. Route tables allow you to define rules about how traffic should be directed. 

2. Border Gateway Protocol (BGP) works with Azure VPN gateways, Azure Route Server, or Azure ExpressRoute to propagate on-premises BGP routes to Azure virtual network.

*Filter network traffic*
Azure virtual networks enable you to filter traffic between subnets by using the following approaches:

1. Network security groups are Azure resources that can contain multiple inbound and outbound security rules. You can define these rules to allow or block traffic, based on factors such as source and destination IP address, port, and protocol.

2. Network virtual appliances are specialized VMs that can be compared to a hardened network appliance. A network virtual appliance carries out a particular network function, such as running a firewall or performing wide area network (WAN) optimization.