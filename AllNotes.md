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

*Connect virtual networks*
You can link virtual networks together by using virtual network **peering**. Peering allows two virtual networks to connect directly to each other. Peering enables resources in each virtual network to communicate with each other. These virtual networks can be in separate regions.

**User-defined routes** (UDR) allow you to control the routing tables between subnets within a virtual network or between virtual networks.

**Note**
Azure virtual networking supports both public(have public Ip address and can be accessed from anywhere in the world.) and private(Have private IP address and can be accessed from within the address space of that virtual network.) endpoints to enable communication between external or internal resources with other internal resources.

## Describe Azure virtual private networks
A virtual private network (VPN) uses an encrypted tunnel within another network. VPNs are typically deployed to connect two or more trusted private networks to one another over an untrusted network (typically the public internet). Traffic is encrypted while traveling over the untrusted network to prevent eavesdropping or other attacks.

### VPN gateways
A VPN gateway is a type of virtual network gateway. Azure VPN Gateway instances are deployed in a dedicated subnet of the virtual network and enable the following connectivity:

1.Connect on-premises datacenters to virtual networks through a site-to-site connection.

2.Connect individual devices to virtual networks through a point-to-site connection.

3.Connect virtual networks to other virtual networks through a network-to-network connection.

All data transfer is encrypted inside a private tunnel as it crosses the internet. You can deploy only one VPN gateway in each virtual network.When setting up a VPN gateway, you must specify the type of VPN - either policy-based or route-based.

1.Policy-based VPN gateways specify statically the IP address of packets that should be encrypted through each tunnel.

2.In Route-based gateways, IPSec tunnels are modeled as a network interface or virtual tunnel interface. IP routing (either static routes or dynamic routing protocols) decides which one of these tunnel interfaces to use when sending each packet. Route-based VPNs are the preferred connection method for on-premises devices

### High-availability scenarios
If you’re configuring a VPN to keep your information safe, you also want to be sure that it’s a highly available and fault tolerant VPN configuration.

*Active/standby*
By default, VPN gateways are deployed as two instances in an active/standby configuration, even if you only see one VPN gateway resource in Azure. When planned maintenance or unplanned disruption affects the active instance, the standby instance automatically assumes responsibility for connections without any user intervention.typically restore within a few seconds for planned maintenance and within 90 seconds for unplanned disruptions.

*Active/Active*
In this configuration, you assign a unique public IP address to each instance. You then create separate tunnels from the on-premises device to each IP address. You can extend the high availability by deploying an additional VPN device on-premises.

*ExpressRoute failover*
Another high-availability option is to configure a VPN gateway as a secure failover path for ExpressRoute connections. In high-availability scenarios, where there's risk associated with an outage of an ExpressRoute circuit, you can also provision a VPN gateway that uses the internet as an alternative method of connectivity.

*Zone-redundant gateways*
In regions that support availability zones, VPN gateways and ExpressRoute gateways can be deployed in a zone-redundant configuration. This configuration brings resiliency, scalability, and higher availability to virtual network gateways. 
These gateways require different gateway stock keeping units (SKUs) and use Standard public IP addresses instead of Basic public IP addresses.

## Describe Azure ExpressRoute
Azure ExpressRoute lets you extend your on-premises networks into the Microsoft cloud over a private connection, with the help of a connectivity provider. This connection is called an ExpressRoute Circuit.  Connectivity can be from an any-to-any (IP VPN) network, a point-to-point Ethernet network, or a virtual cross-connection through a connectivity provider at a colocation facility. ExpressRoute connections don't go over the public Internet. This setup allows ExpressRoute connections to offer more reliability, faster speeds, consistent latencies, and higher security than typical connections over the Internet.

### Features and benefits of ExpressRoute
There are several benefits to using ExpressRoute as the connection service between Azure and on-premises networks.

1.Connectivity to Microsoft cloud services across all regions in the geopolitical region.
            Microsoft Office 365
            Microsoft Dynamics 365
            Azure compute services, such as Azure Virtual Machines
            Azure cloud services, such as Azure Cosmos DB and Azure Storage

2.Global connectivity to Microsoft services across all regions with the ExpressRoute Global Reach.

You can enable ExpressRoute Global Reach to exchange data across your on-premises sites by connecting your ExpressRoute circuits. For example, say you had an office in Asia and a datacenter in Europe, both with ExpressRoute circuits connecting them to the Microsoft network.

3.Dynamic routing between your network and Microsoft via Border Gateway Protocol (BGP).

ExpressRoute uses the BGP. BGP is used to exchange routes between on-premises networks and resources running in Azure. This protocol enables dynamic routing between your on-premises network and services running in the Microsoft cloud.

4.Built-in redundancy in every peering location for higher reliability.

Each connectivity provider uses redundant devices to ensure that connections established with Microsoft are highly available. You can configure multiple circuits to complement this feature.

### ExpressRoute connectivity models
ExpressRoute supports four models that you can use to connect your on-premises network to the Microsoft cloud:

                CloudExchange colocation
                Point-to-point Ethernet connection
                Any-to-any connection
                Directly from ExpressRoute sites

1.CloudExchange colocation

Colocation refers to your datacenter, office, or other facility being physically colocated at a cloud exchange, such as an ISP. If your facility is colocated at a cloud exchange, you can request a virtual cross-connect to the Microsoft cloud.

2.Point-to-point Ethernet connection

Point-to-point ethernet connection refers to using a point-to-point connection to connect your facility to the Microsoft cloud.

3.Any-to-any connection

With any-to-any connectivity, you can integrate your wide area network (WAN) with Azure by providing connections to your offices and datacenters. Azure integrates with your WAN connection to provide a connection like you would have between your datacenter and any branch offices.

4.Directly from ExpressRoute sites

You can connect directly into the Microsoft's global network at a peering location strategically distributed across the world. ExpressRoute Direct provides dual 100 Gbps or 10-Gbps connectivity, which supports Active/Active connectivity at scale.

### Security considerations
With ExpressRoute, your data doesn't travel over the public internet, reducing the risks associated with internet communications. ExpressRoute is a private connection from your on-premises infrastructure to your Azure infrastructure. Even if you have an ExpressRoute connection, DNS queries, certificate revocation list checking, and Azure Content Delivery Network requests are still sent over the public internet.

## Describe Azure DNS
Azure DNS is a hosting service for DNS domains that provides name resolution by using Microsoft Azure infrastructure. By hosting your domains in Azure, you can manage your DNS records using the same credentials, APIs, tools, and billing as your other Azure services.

### Benefits of Azure DNS
Azure DNS uses the scope and scale of Microsoft Azure to provide numerous benefits, including:

                Reliability and performance
                Security
                Ease of Use
                Customizable virtual networks
                Alias records

### Reliability and performance
DNS domains in Azure DNS are hosted on Azure's global network of DNS name servers, providing resiliency and high availability. Azure DNS uses anycast networking, so the closest available DNS server answers each DNS query, providing fast performance and high availability for your domain.

#### Security
Azure DNS is based on Azure Resource Manager, which provides features such as:

1.Azure role-based access control (Azure RBAC) to control who has access to specific actions for your organization.

2.Activity logs to monitor how a user in your organization modified a resource or to find an error when troubleshooting.

3.Resource locking to lock a subscription, resource group, or resource. Locking prevents other users in your organization from accidentally deleting or modifying critical resources.

#### Ease of use
Azure DNS can manage DNS records for your Azure services and provide DNS for your external resources as well. Azure DNS is integrated in the Azure portal and uses the same credentials, support contract, and billing as your other Azure services.

Because Azure DNS is running on Azure, it means you can manage your domains and records with the Azure portal, Azure PowerShell cmdlets, and the cross-platform Azure CLI. Applications that require automated DNS management can integrate with the service by using the REST API and SDKs.

#### Customizable virtual networks with private domains
Azure DNS also supports private DNS domains. This feature allows you to use your own custom domain names in your private virtual networks, rather than being stuck with the Azure-provided names.

#### Alias records
Azure DNS also supports alias record sets. You can use an alias record set to refer to an Azure resource, such as an Azure public IP address, an Azure Traffic Manager profile, or an Azure Content Delivery Network (CDN) endpoint. If the IP address of the underlying resource changes, the alias record set seamlessly updates itself during DNS resolution. The alias record set points to the service instance, and the service instance is associated with an IP address.


# Topic 3 - Azure Storage services
storage account provides a unique namespace for your Azure Storage data that's accessible from anywhere in the world over HTTP or HTTPS. Data in this account is secure, highly available, durable, and massively scalable.

 When you create your storage account, you’ll start by picking the storage account type. Below is a list of redundancy options that will be covered later in this module:

        Locally redundant storage (LRS)
        Geo-redundant storage (GRS)
        Read-access geo-redundant storage (RA-GRS)
        Zone-redundant storage (ZRS)
        Geo-zone-redundant storage (GZRS)
        Read-access geo-zone-redundant storage (RA-GZRS)

**Storage account endpoints**
One of the benefits of using an Azure Storage Account is having a unique namespace in Azure for your data. The combination of the account name and the Azure Storage service endpoint forms the endpoints for your storage account.


