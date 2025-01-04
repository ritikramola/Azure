# Topic One - Azure Core
**Azure Arc** can help manage your cloud environment

## How to work in Sandbox
    1. Powershell
    2.Bash CLI
    3.Use Azure CLI interactive mode

## TWO IMPORTANT PILLAR

    Physical Infrastructure pillar and Management Infrastructure pillar

## Physical Infrastructure Pillar
1.The physical infrastructure for Azure starts with datacenters.

2.Datacenters are grouped into **Azure Regions** or **Azure Availability Zones** that are designed to help you .

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

 When you create your storage account, you'll start by picking the storage account type. Below is a list of redundancy options that will be covered later in this module:

        Locally redundant storage (LRS)
        Geo-redundant storage (GRS)
        Read-access geo-redundant storage (RA-GRS)
        Zone-redundant storage (ZRS)
        Geo-zone-redundant storage (GZRS)
        Read-access geo-zone-redundant storage (RA-GZRS)

**Storage account endpoints**
One of the benefits of using an Azure Storage Account is having a unique namespace in Azure for your data. The combination of the account name and the Azure Storage service endpoint forms the endpoints for your storage account.


## Describe Azure storage redundancy

Azure Storage always stores multiple copies of your data so that it's protected from planned and unplanned events such as transient hardware failures, network or power outages, and natural disasters.The factors that help determine which redundancy option you should choose include:

        How your data is replicated in the primary region.
        Whether your data is replicated to a second region that is geographically distant to the primary region, to protect against regional disasters.
        Whether your application requires read access to the replicated data in the secondary region if the primary region becomes unavailable.

### Redundancy in the primary region
Data in an Azure Storage account is always replicated three times in the primary region. Azure Storage offers two options for how your data is replicated in the primary region, locally redundant storage (LRS) and zone-redundant storage (ZRS).

**Locally redundant storage**
Locally redundant storage (LRS) replicates your data three times within a single data center in the primary region. LRS provides at least 11 nines of durability (99.999999999%) of objects over a given year.

LRS is the lowest-cost redundancy option and offers the least durability compared to other options. LRS protects your data against server rack and drive failures. However, if a disaster such as fire or flooding occurs within the data center, all replicas of a storage account using LRS may be lost or unrecoverable.

**Zone-redundant storage**
For Availability Zone-enabled Regions, zone-redundant storage (ZRS) replicates your Azure Storage data synchronously across three Azure availability zones in the primary region. ZRS offers durability for Azure Storage data objects of at least 12 nines (99.9999999999%) over a given year.

With ZRS, your data is still accessible for both read and write operations even if a zone becomes unavailable.
Microsoft recommends using ZRS in the primary region for scenarios that require high availability. ZRS is also recommended for restricting replication of data within a country or region to meet data governance requirements.

### Redundancy in a secondary region
For applications requiring high durability, you can choose to additionally copy the data in your storage account to a secondary region that is hundreds of miles away from the primary region. If the data in your storage account is copied to a secondary region, then your data is durable even in the event of a catastrophic failure that prevents the data in the primary region from being recovered.

Azure Storage offers two options for copying your data to a secondary region: geo-redundant storage (GRS) and geo-zone-redundant storage (GZRS). 

**Geo-redundant storage**
GRS copies your data synchronously three times within a single physical location in the primary region using LRS. It then copies your data asynchronously to a single physical location in the secondary region (the region pair) using LRS. GRS offers durability for Azure Storage data objects of at least 16 nines (99.99999999999999%) over a given year.

**Geo-zone-redundant storage**
GZRS combines the high availability provided by redundancy across availability zones with protection from regional outages provided by geo-replication. Data in a GZRS storage account is copied across three Azure availability zones in the primary region (similar to ZRS) and is also replicated to a secondary geographic region, using LRS, for protection from regional disasters. Microsoft recommends using GZRS for applications requiring maximum consistency, durability, and availability, excellent performance, and resilience for disaster recovery.
GZRS is designed to provide at least 16 nines (99.99999999999999%) of durability of objects over a given year.

## Describe Azure storage services
The Azure Storage platform includes the following data services:

                Azure Blobs: A massively scalable object store for text and binary data. Also includes support for big data analytics through Data Lake Storage Gen2.
                Azure Files: Managed file shares for cloud or on-premises deployments.
                Azure Queues: A messaging store for reliable messaging between application components.
                Azure Disks: Block-level storage volumes for Azure VMs.
                Azure Tables: NoSQL table option for structured, non-relational data.

### Benefits of Azure Storage
Azure Storage services offer the following benefits for application developers and IT professionals:

1. Durable and highly available. Redundancy ensures that your data is safe if transient hardware failures occur. You can also opt to replicate data across data centers or geographical regions for additional protection from local catastrophes or natural disasters. 

2. Secure. All data written to an Azure storage account is encrypted by the service. Azure Storage provides you with fine-grained control over who has access to your data.

3. Scalable. Azure Storage is designed to be massively scalable to meet the data storage and performance needs of today's applications.

4. Managed. Azure handles hardware maintenance, updates, and critical issues for you.

5. Accessible. Data in Azure Storage is accessible from anywhere in the world over HTTP or HTTPS. Microsoft provides client libraries for Azure Storage in a variety of languages, including .NET, Java, Node.js, Python, PHP, Ruby, Go, and others, as well as a mature REST API. Azure Storage supports scripting in Azure PowerShell or Azure CLI. And the Azure portal and Azure Storage Explorer offer easy visual solutions for working with your data.

#### Azure Blobs
Azure Blob storage is an object storage solution for the cloud. It can store massive amounts of data, such as text or binary data. Azure Blob storage is unstructured, meaning that there are no restrictions on the kinds of data it can hold.One advantage of blob storage over disk storage is that it doesn't require developers to think about or manage disks.

Blob storage is ideal for:

                Serving images or documents directly to a browser.
                Storing files for distributed access.
                Streaming video and audio.
                Storing data for backup and restore, disaster recovery, and archiving.
                Storing data for analysis by an on-premises or Azure-hosted service.

**Accessing blob storage**
Objects in blob storage can be accessed from anywhere in the world via HTTP or HTTPS. Users or client applications can access blobs via URLs, the Azure Storage REST API, Azure PowerShell, Azure CLI, or an Azure Storage client library.


#### Blob storage tiers
Data stored in the cloud can grow at an exponential pace. To manage costs for your expanding storage needs, it's helpful to organize your data based on attributes like frequency of access and planned retention period. Data stored in the cloud can be handled differently based on how it's generated, processed, and accessed over its lifetime.
To accommodate these different access needs, Azure provides several access tiers, which you can use to balance your storage costs with your access needs.Azure Storage offers different access tiers for your blob storage, helping you store object data in the most cost-effective manner.

1.*Hot access tier*: Optimized for storing data that is accessed frequently (for example, images for your website).

2. *Cool access tier*: Optimized for data that is infrequently accessed and stored for at least 30 days (for example, invoices for your customers).

3. *Cold access tier*: Optimized for storing data that is infrequently accessed and stored for at least 90 days.

4. *Archive access tier*: Appropriate for data that is rarely accessed and stored for at least 180 days, with flexible latency requirements (for example, long-term backups).

### Azure Files
Azure File storage offers fully managed file shares in the cloud that are accessible via the industry standard *Server Message Block* (SMB) or *Network File System* (NFS) protocols. Azure Files file shares can be mounted concurrently by cloud or on-premises deployments. SMB Azure file shares are accessible from Windows, Linux, and macOS clients. NFS Azure Files shares are accessible from Linux or macOS clients. 

Azure Files key benefits:

1. Shared access: Azure file shares support the industry standard SMB and NFS protocols, meaning you can seamlessly replace your on-premises file shares with Azure file shares without worrying about application compatibility.

2. Fully managed: Azure file shares can be created without the need to manage hardware or an OS. This means you don't have to deal with patching the server OS with critical security upgrades or replacing faulty hard disks.

3. Scripting and tooling: PowerShell cmdlets and Azure CLI can be used to create, mount, and manage Azure file shares as part of the administration of Azure applications. You can create and manage Azure file shares using Azure portal and Azure Storage Explorer.

4. Resiliency: Azure Files has been built from the ground up to always be available. Replacing on-premises file shares with Azure Files means you don't have to wake up in the middle of the night to deal with local power outages or network issues.

5. Familiar programmability: Applications running in Azure can access data in the share via file system I/O APIs. Developers can therefore use their existing code and skills to migrate existing applications. In addition to System IO APIs, you can use Azure Storage Client Libraries or the Azure Storage REST API.

### Azure Queues
Azure Queue storage is a service for storing large numbers of messages. Once stored, you can access the messages from anywhere in the world via authenticated calls using HTTP or HTTPS. A queue can contain as many messages as your storage account has room for (potentially millions). Each individual message can be up to 64 KB in size. Queues are commonly used to create a backlog of work to process asynchronously.

### Azure Disks
Azure Disk storage, or Azure managed disks, are block-level storage volumes managed by Azure for use with Azure VMs. Conceptually, they’re the same as a physical disk, but they’re virtualized – offering greater resiliency and availability than a physical disk.

### Azure Tables
Azure Table storage stores large amounts of structured data. Azure tables are a NoSQL datastore that accepts authenticated calls from inside and outside the Azure cloud. This enables you to use Azure tables to build your hybrid or multicloud solution and have your data always available. Azure tables are ideal for storing structured, non-relational data.

## Identify Azure data migration options
Azure supports both real-time migration of infrastructure, applications, and data using Azure Migrate as well as asynchronous migration of data using Azure Data Box.

### Azure Migrate
Azure Migrate is a service that helps you migrate from an on-premises environment to the cloud. Azure Migrate functions as a hub to help you manage the assessment and migration of your on-premises datacenter to Azure. It provides the following:

1.Unified migration platform: A single portal to start, run, and track your migration to Azure.

2.Range of tools: A range of tools for assessment and migration. Azure Migrate tools include Azure Migrate: Discovery and assessment and Azure Migrate: Server Migration. Azure Migrate also integrates with other Azure services and tools, and with independent software vendor (ISV) offerings.

3.Assessment and migration: In the Azure Migrate hub, you can assess and migrate your on-premises infrastructure to Azure.

#### Integrated tools
In addition to working with tools from ISVs, the Azure Migrate hub also includes the following tools to help with migration:

1.Azure Migrate: Discovery and assessment. Discover and assess on-premises servers running on VMware, Hyper-V, and physical servers in preparation for migration to Azure.

2.Azure Migrate: Server Migration. Migrate VMware VMs, Hyper-V VMs, physical servers, other virtualized servers, and public cloud VMs to Azure.

3.Data Migration Assistant. Data Migration Assistant is a stand-alone tool to assess SQL Servers. It helps pinpoint potential problems blocking migration. It identifies unsupported features, new features that can benefit you after migration, and the right path for database migration.

4.Azure Database Migration Service. Migrate on-premises databases to Azure VMs running SQL Server, Azure SQL Database, or SQL Managed Instances.

5.Azure App Service migration assistant. It is a standalone tool to assess on-premises websites for migration to Azure App Service. Use Migration Assistant to migrate .NET and PHP web apps to Azure.

6.Azure Data Box. Use Azure Data Box products to move large amounts of offline data to Azure.


### Azure Data Box
Azure Data Box is a physical migration service that helps transfer large amounts of data in a quick, inexpensive, and reliable way. The secure data transfer is accelerated by shipping you a proprietary Data Box storage device that has a maximum usable storage capacity of 80 terabytes. The Data Box is transported to and from your datacenter via a regional carrier.

#### Use cases
Data Box is ideally suited to transfer data sizes larger than 40 TBs in scenarios with no to limited network connectivity. The data movement can be one-time, periodic, or an initial bulk data transfer followed by periodic transfers.

Here are the various scenarios where Data Box can be used to import data to Azure.

        Onetime migration - when a large amount of on-premises data is moved to Azure.
        Moving a media library from offline tapes into Azure.
        Migrating your VM farm, SQL server, and applications to Azure.
        Moving historical data to Azure for in-depth analysis and reporting using HDInsight.
        Initial bulk transfer - when an initial bulk transfer is done using Data Box (seed) followed by incremental transfers over the network.
        Periodic uploads - when large amount of data is generated periodically and needs to be moved to Azure.

Here are the various scenarios where Data Box can be used to export data from Azure.

        Disaster recovery - when a copy of the data from Azure is restored to an on-premises network. In a typical disaster recovery scenario, a large amount of Azure data is exported to a Data Box. Microsoft then ships this Data Box, and the data is restored on your premises in a short time.
        Security requirements - when you need to be able to export data out of Azure due to government or security requirements.
        Migrate back to on-premises or to another cloud service provider - when you want to move all the data back to on-premises, or to another cloud service provider, export data via Data Box to migrate the workloads.

## Identify Azure file movement options
 Azure also has tools designed to help you move or interact with individual files or small file groups. Among those tools are AzCopy, Azure Storage Explorer, and Azure File Sync.

### AzCopy
AzCopy is a command-line utility that you can use to copy blobs or files to or from your storage account. With AzCopy, you can upload files, download files, copy files between storage accounts, and even synchronize files. AzCopy can even be configured to work with other cloud providers to help move files back and forth between clouds.

### Azure Storage Explorer
Azure Storage Explorer is a standalone app that provides a graphical interface to manage files and blobs in your Azure Storage Account. It works on Windows, macOS, and Linux operating systems and uses AzCopy on the backend to perform all of the file and blob management tasks. With Storage Explorer, you can upload to Azure, download from Azure, or move between storage accounts.

### Azure File Sync
Azure File Sync is a tool that lets you centralize your file shares in Azure Files and keep the flexibility, performance, and compatibility of a Windows file server. Once you install Azure File Sync on your local Windows server, it will automatically stay bi-directionally synced with your files in Azure.

# Topic 4 - Security Access in Azure

## Describe Azure directory services
Microsoft Entra ID is a directory service that enables you to sign in and access both Microsoft cloud applications and cloud applications that you develop. Microsoft Entra ID can also help you maintain your on-premises Active Directory deployment.
Microsoft Entra ID is Microsoft's cloud-based identity and access management service. With Microsoft Entra ID, you control the identity accounts, but Microsoft ensures that the service is available globally.

### Who uses Microsoft Entra ID?
Microsoft Entra ID is for:

1.IT administrators use Microsoft Entra ID to control access to applications and resources based on their business requirements.

2.App developers. use Microsoft Entra ID to provide a standards-based approach for adding functionality to applications that they build.

3.Users. Users can manage their identities and take maintenance actions like self-service password reset.
Online service subscribers. Microsoft 365, Microsoft Office 365, Azure, and Microsoft Dynamics CRM Online subscribers are already using Microsoft Entra ID to authenticate into their account.

### What does Microsoft Entra ID do?
Microsoft Entra ID provides services such as:
1.Authentication: This includes verifying identity to access applications and resources. It also includes providing functionality such as self-service password reset, multifactor authentication.

2.Single sign-on: Single sign-on (SSO) enables you to remember only one username and one password to access multiple applications. A single identity is tied to a user, which simplifies the security model. As users change roles or leave an organization, access modifications are tied to that identity.

3.Application management: You can manage your cloud and on-premises apps by using Microsoft Entra ID. Features like Application Proxy, SaaS apps, the My Apps portal, and single sign-on provide a better user experience.

4.Device management: Along with accounts for individual people, Microsoft Entra ID supports the registration of devices. Registration enables devices to be managed through tools like Microsoft Intune. It also allows for device-based Conditional Access policies to restrict access attempts to only those coming from known devices, regardless of the requesting user account.

### Can I connect my on-premises AD with Microsoft Entra ID?
If you had an on-premises environment running Active Directory and a cloud deployment using Microsoft Entra ID, you would need to maintain two identity sets. However, you can connect Active Directory with Microsoft Entra ID, enabling a consistent identity experience between cloud and on-premises.Microsoft Entra Connect synchronizes user identities between on-premises Active Directory and Microsoft Entra ID.

## What is Microsoft Entra Domain Services?
Microsoft Entra Domain Services is a service that provides managed domain services such as domain join, group policy, lightweight directory access protocol (LDAP), and Kerberos/NTLM authentication. With Microsoft Entra Domain Services, you get the benefit of domain services without the need to deploy, manage, and patch domain controllers (DCs) in the cloud.

### How does Microsoft Entra Domain Services work?
When you create a Microsoft Entra Domain Services managed domain, you define a unique namespace. This namespace is the domain name. Two Windows Server domain controllers are then deployed into your selected Azure region. This deployment of DCs is known as a replica set.

### Is information synchronized?
A managed domain is configured to perform a one-way synchronization from Microsoft Entra ID to Microsoft Entra Domain Services. You can create resources directly in the managed domain, but they aren't synchronized back to Microsoft Entra ID. In a hybrid environment with an on-premises AD DS environment, Microsoft Entra Connect synchronizes identity information with Microsoft Entra ID, which is then synchronized to the managed domain.

## Describe Azure authentication methods
Authentication is the process of establishing the identity of a person, service, or device. It requires the person, service, or device to provide some type of credential to prove who they are. Authentication is like presenting ID when you’re traveling. Azure supports multiple authentication methods, including standard passwords, single sign-on (SSO), multifactor authentication (MFA), and passwordless.

### What's single sign-on?
Single sign-on (SSO) enables a user to sign in one time and use that credential to access multiple resources and applications from different providers. For SSO to work, the different applications and providers must trust the initial authenticator.

With SSO, you need to remember only one ID and one password. Access across applications is granted to a single identity that's tied to the user, which simplifies the security model. As users change roles or leave an organization, access is tied to a single identity.

## What’s multifactor authentication?
Multifactor authentication is the process of prompting a user for an extra form (or factor) of identification during the sign-in process. MFA helps protect against a password compromise in situations where the password was compromised but the second factor wasn't.

Multifactor authentication provides additional security for your identities by requiring two or more elements to fully authenticate. These elements fall into three categories:

1.Something the user knows – this might be a challenge question.

2.Something the user has – this might be a code that's sent to the user's mobile phone.

3.Something the user is – this is typically some sort of biometric property, such as a fingerprint or face scan.

#### What's Microsoft Entra multifactor authentication?
 Microsoft Entra multifactor authentication enables users to choose an additional form of authentication during sign-in, such as a phone call or mobile app notification.

 ### What’s passwordless authentication?
With Features like MFA users often get frustrated with the additional security layer on top of having to remember their passwords. Passwordless authentication methods are more convenient because the password is removed and replaced with something you have, plus something you are, or something you know.

Passwordless authentication needs to be set up on a device before it can work. For example, your computer is something you have. Once it’s been registered or enrolled, Azure now knows that it’s associated with you.

Each organization has different needs when it comes to authentication. Microsoft global Azure and Azure Government offer the following three passwordless authentication options that integrate with Microsoft Entra ID:

        Windows Hello for Business
        Microsoft Authenticator app
        FIDO2 security keys

#### Windows Hello for Business
Windows Hello for Business is ideal for information workers that have their own designated Windows PC. The biometric and PIN credentials are directly tied to the user's PC, which prevents access from anyone other than the owner. With public key infrastructure (PKI) integration and built-in support for single sign-on (SSO), Windows Hello for Business provides a convenient method for seamlessly accessing corporate resources on-premises and in the cloud.

#### Microsoft Authenticator App
You can also allow your employee's phone to become a passwordless authentication method. You may already be using the Microsoft Authenticator App as a convenient multifactor authentication option in addition to a password. You can also use the Authenticator App as a passwordless option.

#### FIDO2 security keys
The FIDO (Fast IDentity Online) Alliance helps to promote open authentication standards and reduce the use of passwords as a form of authentication. FIDO2 is the latest standard that incorporates the web authentication (WebAuthn) standard.FIDO allows users and organizations to leverage the standard to sign-in to their resources without a username or password by using an external security key or a platform key built into a device.

These FIDO2 security keys are typically USB devices, but could also use Bluetooth or NFC.

## Describe Azure external identities
An external identity is a person, device, service, etc. that is outside your organization. Microsoft Entra External ID refers to all the ways you can securely interact with users outside of your organization. If you want to collaborate with partners, distributors, suppliers, or vendors, you can share your resources and define how your internal users can access external organizations.

The external user’s identity provider manages their identity, and you manage access to your apps with Microsoft Entra ID or Azure AD B2C to keep your resources protected.

The following capabilities make up External Identities:

1.Business to business (B2B) collaboration - Collaborate with external users by letting them use their preferred identity to sign-in to your Microsoft applications or other enterprise applications (SaaS apps, custom-developed apps, etc.).

2.B2B direct connect - Establish a mutual, two-way trust with another Microsoft Entra organization for seamless collaboration. B2B direct connect currently supports Teams shared channels, enabling external users to access your resources from within their home instances of Teams.

3.Microsoft Azure Active Directory business to customer (B2C) - Publish modern SaaS apps or custom-developed apps (excluding Microsoft apps) to consumers and customers, while using Azure AD B2C for identity and access management.
Depending on how you want to interact with external organizations and the types of resources you need to share, you can use a combination of these capabilities.

## Describe Azure conditional access
Conditional Access is a tool that Microsoft Entra ID uses to allow (or deny) access to resources based on identity signals. These signals include who the user is, where the user is, and what device the user is requesting access from.

Conditional Access also provides a more granular multifactor authentication experience for users.During sign-in, Conditional Access collects signals from the user, makes decisions based on those signals, and then enforces that decision by allowing or denying the access request or challenging for a multifactor authentication response.

### When can I use Conditional Access?
Conditional Access is useful when you need to:

1.Require multifactor authentication (MFA) to access an application depending on the requester’s role, location, or network.

2.Require access to services only through approved client applications.eg. limited email access

3.Require users to access your application only from managed devices. A managed device is a device that meets your standards for security and compliance.

4.Block access from untrusted sources, such as access from unknown or unexpected locations.

## Describe Azure role-based access control
When you have multiple IT and engineering teams, how can you control what access they have to the resources in your cloud environment? The principle of least privilege says you should only grant access up to the level needed to complete a task.

However, managing that level of permissions for an entire team would become tedious. Instead of defining the detailed access requirements for each individual, and then updating access requirements when new resources are created or new people join the team, Azure enables you to control access through **Azure role-based access control** (Azure RBAC).

Azure provides built-in roles that describe common access rules for cloud resources. You can also define your own roles. Each role has an associated set of access permissions that relate to that role. So, if you hire a new engineer and add them to the Azure RBAC group for engineers, they automatically get the same access as the other engineers in the same Azure RBAC group.

### How is role-based access control applied to resources?
Role-based access control is applied to a scope, which is a resource or set of resources that this access applies to.

A management group, subscription, or resource group might be given the role of owner, so they have increased control and authority. An observer, who isn't expected to make any updates, might be given a role of Reader for the same scope, enabling them to review or observe the management group, subscription, or resource group.

zure RBAC is hierarchical, in that when you grant access at a parent scope, those permissions are inherited by all child scopes.

1.When you assign the Owner role to a user at the management group scope, that user can manage everything in all subscriptions within the management group.

2.When you assign the Reader role to a group at the subscription scope, the members of that group can view every resource group and resource within the subscription.

### How is Azure RBAC enforced?
Azure RBAC is enforced on any action that's initiated against an Azure resource that passes through Azure Resource Manager. Resource Manager is a management service that provides a way to organize and secure your cloud resources.

You typically access Resource Manager from the Azure portal, Azure Cloud Shell, Azure PowerShell, and the Azure CLI. Azure RBAC doesn't enforce access permissions at the application or data level. Application security must be handled by your application.

Azure RBAC uses an allow model. When you're assigned a role, Azure RBAC allows you to perform actions within the scope of that role. If one role assignment grants you read permissions to a resource group and a different role assignment grants you write permissions to the same resource group, you have both read and write permissions on that resource group.

## Describe Zero Trust model
Zero Trust is a security model that assumes the worst case scenario and protects resources with that expectation. Zero Trust assumes breach at the outset, and then verifies each request as though it originated from an uncontrolled network.

To address the new world of computing, Microsoft highly recommends the Zero Trust security model, which is based on these guiding principles:

1.Verify explicitly - Always authenticate and authorize based on all available data points.

2.Use least privilege access - Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection.
        
3.Assume breach - Minimize blast radius and segment access. Verify end-to-end encryption. Use analytics to get visibility, drive threat detection, and improve defenses.


### Adjusting to Zero Trust
The Zero Trust model flips that scenario. Instead of assuming that a device is safe because it’s within the corporate network, it requires everyone to authenticate. Then grants access based on authentication rather than location.

## Describe defense-in-depth
The objective of defense-in-depth is to protect information and prevent it from being stolen by those who aren't authorized to access it.

A defense-in-depth strategy uses a series of mechanisms to slow the advance of an attack that aims at acquiring unauthorized access to data.

### Layers of defense-in-depth
You can visualize defense-in-depth as a set of layers, with the data to be secured at the center and all the other layers functioning to protect that central data layer.

From the center: data, application, compute, network, perimeter, identity & access, physical security.

Each layer provides protection so that if one layer is breached, a subsequent layer is already in place to prevent further exposure. This approach removes reliance on any single layer of protection. It slows down an attack and provides alert information that security teams can act upon, either automatically or manually.

Here's a brief overview of the role of each layer:

1.The **physical security layer** is the first line of defense to protect computing hardware in the datacenter.

2.The **identity and access layer** controls access to infrastructure and change control.the access is granted only to what's needed, and that sign-in events and changes are logged.

3.The **perimeter layer** uses distributed denial of service (DDoS) protection to filter large-scale attacks before they can cause a denial of service for users.

4.The **network layer** limits communication between resources through segmentation and access controls.

5.The **compute layer** secures access to virtual machines.

6.The **application layer** helps ensure that applications are secure and free of security vulnerabilities.

7.The **data layer** controls access to business and customer data that you need to protect.

8.These layers provide a guideline for you to help make security configuration decisions in all of the layers of your applications.

## Describe Microsoft Defender for Cloud
Defender for Cloud is a monitoring tool for security posture management and threat protection. It monitors your cloud, on-premises, hybrid, and multicloud environments to provide guidance and notifications aimed at strengthening your security posture.

Defender for Cloud provides the tools needed to harden your resources, track your security posture, protect against cyber attacks, and streamline security management. Deployment of Defender for Cloud is easy, it’s already natively integrated to Azure.

#### Azure-native protections
Defender for Cloud helps you detect threats across:

1.Azure PaaS services – Detect threats targeting Azure services including Azure App Service, Azure SQL, Azure Storage Account, and more data services. You can also perform anomaly detection on your Azure activity logs.

2.Azure data services – Defender for Cloud includes capabilities that help you automatically classify your data in Azure SQL. You can also get assessments for potential vulnerabilities across Azure SQL and Storage services, and recommendations for how to mitigate them.

3.Networks – Defender for Cloud helps you limit exposure to brute force attacks. By reducing access to virtual machine ports, using the just-in-time VM access, you can harden your network by preventing unnecessary access. You can set secure access policies on selected ports, for only authorized users, allowed source IP address ranges or IP addresses, and for a limited amount of time.

#### Defend your hybrid resources
In addition to defending your Azure environment, you can add Defender for Cloud capabilities to your hybrid cloud environment to protect your non-Azure servers. To help you focus on what matters the most, you'll get customized threat intelligence and prioritized alerts according to your specific environment.

#### Defend resources running on other clouds
Defender for Cloud can also protect resources in other clouds (such as AWS and GCP).

1.Defender for Cloud's CSPM features extend to your AWS resources.Defender for Cloud's asset inventory page is a multicloud enabled feature helping you manage your AWS resources alongside your Azure resources.

.Microsoft Defender for Containers extends its container threat detection and advanced defenses to your Amazon EKS Linux clusters.

3.Microsoft Defender for Servers brings threat detection and advanced defenses to your Windows and Linux EC2 instances.

#### Continuously assess
Defender for cloud helps you continuously assess your environment. Defender for Cloud includes vulnerability assessment solutions for your virtual machines, container registries, and SQL servers.

Microsoft Defender for servers includes automatic, native integration with Microsoft Defender for Endpoint. With this integration enabled, you'll have access to the vulnerability findings from Microsoft threat and vulnerability management.

#### Secure
From authentication methods to access control to the concept of Zero Trust, security in the cloud is an essential basic that must be done right. In order to be secure in the cloud, you have to ensure your workloads are secure. To secure your workloads, you need security policies in place Because policies in Defender for Cloud are built on top of Azure Policy controls, you're getting the full range and flexibility of a world-class policy solution.

One of the benefits of moving to the cloud is the ability to grow and scale as you need, adding new services and resources as necessary. Defender for Cloud is constantly monitoring for new resources being deployed across your workloads. Defender for Cloud assesses if new resources are configured according to security best practices.

The list of recommendations is enabled and supported by the Azure Security Benchmark. This Microsoft-authored, Azure-specific, benchmark provides a set of guidelines for security and compliance best practices based on common compliance frameworks.

#### Defend

The first two areas were focused on assessing, monitoring, and maintaining your environment. Defender for Cloud also helps you defend your environment by providing security alerts and advanced threat protection features.

**Security alerts**
When Defender for Cloud detects a threat in any area of your environment, it generates a security alert. Security alerts:

1.Describe details of the affected resources

2.Suggest remediation steps

3.Provide, in some cases, an option to trigger a logic app in response

Whether an alert is generated by Defender for Cloud or received by Defender for Cloud from an integrated security product, you can export it. Defender for Cloud's threat protection includes fusion kill-chain analysis, which automatically correlates alerts in your environment based on cyber kill-chain analysis, to help you better understand the full story of an attack campaign, where it started, and what kind of impact it had on your resources.

**Advanced threat protection**
Defender for cloud provides advanced threat protection features for many of your deployed resources, including virtual machines, SQL databases, containers, web applications, and your network. Protections include securing the management ports of your VMs with just-in-time access, and adaptive application controls to create allowlists for what apps should and shouldn't run on your machines.

# Topic 5 : Azure Cost management

## Describe factors that can affect costs in Azure
Azure shifts development costs from the capital expense (CapEx) of building out and maintaining infrastructure and facilities to an operational expense (OpEx) of renting infrastructure as you need it, whether it’s compute, storage, networking, and so on.

That OpEx cost can be impacted by many factors. Some of the impacting factors are:

    Resource type
    Consumption 
    Maintenance
    Geography   
    Subscription type
    Azure Marketplace

### Resource Type
A number of factors influence the cost of Azure resources. The type, the settings, and the Azure region will all have an impact on how much a resource costs. Azure creates metered instances for that resource. The meters track the resources' usage and generate a usage record that is used to calculate your bill.

**Example**
With a storage account, you specify a type such as blob, a performance tier, an access tier, redundancy settings, and a region. Creating the same storage account in different regions may show different costs and changing any of the settings may also impact the price.

### Consumption
Pay-as-you-go has been a consistent theme throughout, and that’s the cloud payment model where you pay for the resources that you use during a billing cycle. If you use more compute this cycle, you pay more. If you use less in the current cycle, you pay less. It’s a straight forward pricing mechanism that allows for maximum flexibility.

However, Azure also offers the ability to commit to using a set amount of cloud resources in advance and receiving discounts on those “reserved” resources.

### Maintenance
The flexibility of the cloud makes it possible to rapidly adjust resources based on demand. Using resource groups can help keep all of your resources organized. In order to control costs, it’s important to maintain your cloud environment. By keeping an eye on your resources and making sure you’re not keeping around resources that are no longer needed, you can help control cloud costs.

## Geography
When you provision most resources in Azure, you need to define a region where the resource deploys. Azure infrastructure is distributed globally, which enables you to deploy your services centrally or closest to your customers, or something in between. With this global deployment comes global pricing differences. The cost of power, labor, taxes, and fees vary depending on the location.

### Network Traffic
Billing zones are a factor in determining the cost of some Azure services.

Bandwidth refers to data moving in and out of Azure datacenters. Some inbound data transfers (data coming into Azure datacenters) are free. For outbound data transfers (data leaving Azure datacenters), data transfer pricing is based on zones.

A zone is a geographical grouping of Azure regions for billing purposes. The bandwidth pricing page has additional information on pricing for data ingress, egress, and transfer.

### Subscription type
Some Azure subscription types also include usage allowances, which affect costs.

For example, an Azure free trial subscription provides access to a number of Azure products that are free for 12 months.

### Azure Marketplace
Azure Marketplace lets you purchase Azure-based solutions and services from third-party vendors. This could be a server with software preinstalled and configured, or managed network firewall appliances, or connectors to third-party backup services. When you purchase products through Azure Marketplace, you may pay for not only the Azure services that you’re using, but also the services or expertise of the third-party vendor. Billing structures are set by the vendor

### Compare the Pricing and Total Cost of Ownership calculators
The pricing calculator and the total cost of ownership (TCO) calculator are two calculators that help you understand potential Azure expenses. Both calculators are accessible from the internet, and both calculators allow you to build out a configuration. However, the two calculators have very different purposes.

#### Pricing calculator
The pricing calculator is designed to give you an estimated cost for provisioning resources in Azure. You can get an estimate for individual resources, build out a solution, or use an example scenario to see an estimate of the Azure spend. The pricing calculator’s focus is on the cost of provisioned resources in Azure.

**Note**
The Pricing calculator is for information purposes only. The prices are only an estimate. Nothing is provisioned when you add resources to the pricing calculator, and you won't be charged for any services you select.

#### TCO(total cost of ownership) calculator
With the TCO calculator, you enter your configuration, add in assumptions like power and IT labor costs, and are presented with an estimation of the cost difference to run the same environment in your current datacenter or in Azure.

### Define your requirements
Before you run the Pricing calculator, you need a sense of what Azure services you need.

For a basic web application hosted in your datacenter, you might run a configuration similar to the following.

An ASP.NET web application that runs on Windows. The web application provides information about product inventory and pricing. There are two virtual machines that are connected through a central load balancer. The web application connects to a SQL Server database that holds inventory and pricing information.

To migrate to Azure, you might:

    Use Azure Virtual Machines instances, similar to the virtual machines used in your datacenter.
    Use Azure Application Gateway for load balancing.
    Use Azure SQL Database to hold inventory and pricing information.

In practice, you would define your requirements in greater detail. But here are some basic facts and requirements to get you started:

    The application is used internally. It's not accessible to customers.
    This application doesn't require a massive amount of computing power.   
    The virtual machines and the database run all the time (730 hours per month).
    The network processes about 1 TB of data per month.
    The database doesn't need to be configured for high-performance workloads and requires no more than 32 GB of storage.

### Describe the Microsoft Cost Management tool
Microsoft Azure is a global cloud provider, meaning you can provision resources anywhere in the world. You can provision resources rapidly to meet a sudden demand, or to test out a new feature, or on accident. If you accidentally provision new resources, you may not be aware of them until it’s time for your invoice. Cost Management is a service that helps avoid those situations.

### What is Cost Management?
Cost Management provides the ability to quickly check Azure resource costs, create alerts based on resource spend, and create budgets that can be used to automate management of resources.

Cost analysis is a subset of Cost Management that provides a quick visual for your Azure costs. Using cost analysis, you can quickly view the total cost in a variety of different ways, including by billing cycle, region, resource, and so on.

You use cost analysis to explore and analyze your organizational costs. You can view aggregated costs by organization to understand where costs are accrued and to identify spending trends.

### Cost alerts
Cost alerts provide a single location to quickly check on all of the different alert types that may show up in the Cost Management service. The three types of alerts that may show up are:

    Budget alerts
    Credit alerts
    Department spending quota alerts.

#### Budget alerts
Budget alerts notify you when spending, based on usage or cost, reaches or exceeds the amount defined in the alert condition of the budget. Cost Management budgets are created using the Azure portal or the Azure Consumption API.

In the Azure portal, budgets are defined by cost or by consumption usage when using the Azure Consumption API. Budget alerts support both cost-based and usage-based budgets.You can view all cost alerts in the **Azure portal**.

#### Credit alerts
Credit alerts notify you when your Azure credit monetary commitments are consumed. Monetary commitments are for organizations with Enterprise Agreements (EAs). Credit alerts are generated automatically at 90% and at 100% of your Azure credit balance. Whenever an alert is generated, it's reflected in cost alerts, and in the email sent to the account owners.

#### Department spending quota alerts
Department spending quota alerts notify you when department spending reaches a fixed threshold of the quota. Spending quotas are configured in the EA portal. Whenever a threshold is met, it generates an email to department owners, and appears in cost alerts.

### Budgets
A budget is where you set a spending limit for Azure. You can set budgets based on a subscription, resource group, service type, or other criteria. When you set a budget, you will also set a budget alert. When the budget hits the budget alert level, it will trigger a budget alert that shows up in the cost alerts area.

A more advanced use of budgets enables budget conditions to trigger automation that suspends or otherwise modifies resources once the trigger condition has occurred.

## Describe the purpose of tags
As your cloud usage grows, it's increasingly important to stay organized. A good organization strategy helps you understand your cloud usage and can help you manage costs.

Resource tags are another way to organize resources. Tags provide extra information, or metadata, about your resources. This metadata is useful for:

1.Resource management: Tags enable you to locate and act on resources that are associated with specific workloads, environments, business units, and owners.

2.Cost management and optimization :Tags enable you to group resources so that you can report on costs, allocate internal cost centers, track budgets, and forecast estimated cost.

3.Operations management: Tags enable you to group resources according to how critical their availability is to your business. This grouping helps you formulate service-level agreements (SLAs). An SLA is an uptime or performance guarantee between you and your users.

4.Security : Tags enable you to classify data by its security level, such as public or confidential.

5.Governance and regulatory compliance: Tags enable you to identify resources that align with governance or regulatory compliance requirements, such as ISO 27001. Tags can also be part of your standards enforcement efforts. For example, you might require that all resources be tagged with an owner or department name.

6.Workload optimization and automation: Tags can help you visualize all of the resources that participate in complex deployments. 

### How do I manage resource tags?
You can add, modify, or delete resource tags through Windows PowerShell, the Azure CLI, Azure Resource Manager templates, the REST API, or the Azure portal.

You can use Azure Policy to enforce tagging rules and conventions. For example, you can require that certain tags be added to new resources as they're provisioned. You can also define rules that reapply tags that have been removed. Resources don't inherit tags from subscriptions and resource groups, meaning that you can apply tags at one level and not have those tags automatically show up at a different level, allowing you to create custom tagging schemas that change depending on the level (resource, resource group, subscription, and so on).

# Topic 6 :  features and tools in Azure

## Describe the purpose of Microsoft Purview
Microsoft Purview is a family of data governance, risk, and compliance solutions that helps you get a single, unified view into your data.Microsoft Purview brings insights about your on-premises, multicloud, and software-as-a-service data together.

Two main solution areas comprise Microsoft Purview: risk and compliance and unified data governance.

### Microsoft Purview risk and compliance solutions
Microsoft 365 features as a core component of the Microsoft Purview risk and compliance solutions. Microsoft Teams, OneDrive, and Exchange are just some of the Microsoft 365 services that Microsoft Purview uses to help manage and monitor your data. 

    Protect sensitive data across clouds, apps, and devices.
    Identify data risks and manage regulatory compliance requirements.
    Get started with regulatory compliance.

###  Microsoft Purview Unified data governance
Microsoft Purview has robust, unified data governance solutions that help manage your on-premises, multicloud, and software as a service data. Microsoft Purview’s robust data governance capabilities enable you to manage your data stored in Azure, SQL and Hive databases, locally, and even in other clouds like Amazon S3.

Microsoft Purview’s unified data governance helps your organization:

    Create an up-to-date map of your entire data estate that includes data classification and end-to-end lineage.
    Identify where sensitive data is stored in your estate.
    Create a secure environment for data consumers to find valuable data.
    Generate insights about how your data is stored and used.
    Manage access to the data in your estate securely and at scale.

## Describe the purpose of Azure Policy
Azure Policy is a service in Azure that enables you to create, assign, and manage policies that control or audit your resources. These policies enforce different rules across your resource configurations so that those configurations stay compliant with corporate standards.

How does Azure Policy define policies?

Azure Policy enables you to define both individual policies and groups of related policies, known as initiatives. Azure Policy evaluates your resources and highlights resources that aren't compliant with the policies you've created. Azure Policy can also prevent noncompliant resources from being created.

Azure Policies can be set at each level, enabling you to set policies on a specific resource, resource group, subscription, and so on. Additionally, Azure Policies are inherited, so if you set a policy at a high level, it will automatically be applied to all of the groupings that fall within the parent.

Azure Policy comes with built-in policy and initiative definitions for Storage, Networking, Compute, Security Center, and Monitoring.

Azure Policy also integrates with Azure DevOps by applying any continuous integration and delivery pipeline policies that pertain to the pre-deployment and post-deployment phases of your applications.

### What are Azure Policy initiatives?
An Azure Policy initiative is a way of grouping related policies together. The initiative definition contains all of the policy definitions to help track your compliance state for a larger goal.

## Describe the purpose of resource locks
A resource lock prevents resources from being accidentally deleted or changed.

Even with Azure role-based access control (Azure RBAC) policies in place, there's still a risk that people with the right level of access could delete critical cloud resources. Resource locks prevent resources from being deleted or updated, depending on the type of lock. Resource locks can be applied to individual resources, resource groups, or even an entire subscription

### Types of Resource Locks
There are two types of resource locks, one that prevents users from deleting and one that prevents users from changing or deleting a resource.

1.Delete means authorized users can still read and modify a resource, but they can't delete the resource.

2.ReadOnly means authorized users can read a resource, but they can't delete or update the resource. Applying this lock is similar to restricting all authorized users to the permissions granted by the Reader role.

### How do I manage resource locks?
You can manage resource locks from the Azure portal, PowerShell, the Azure CLI, or from an Azure Resource Manager template.

To view, add, or delete locks in the Azure portal, go to the Settings section of any resource's Settings pane in the Azure portal.

## Describe the purpose of the Service Trust portal
The Microsoft Service Trust Portal is a portal that provides access to various content, tools, and other resources about Microsoft security, privacy, and compliance practices.

The Service Trust Portal contains details about Microsoft's implementation of controls and processes that protect our cloud services and the customer data therein. To access some of the resources on the Service Trust Portal, you must sign in as an authenticated user with your Microsoft cloud services account (Microsoft Entra organization account).

### Accessing the Service Trust Portal
The Service Trust Portal features and content are accessible from the main menu. The categories on the main menu are:

Service Trust Portal provides a quick access hyperlink to return to the Service Trust Portal home page.
My Library lets you save (or pin) documents to quickly access them on your My Library page.
All Documents is a single landing place for documents on the service trust portal. 

# Topic 7 : Azure Management and deployment

## Describe tools for interacting with Azure
To get the most out of Azure, you need a way to interact with the Azure environment, the management groups, subscriptions, resource groups, resources, and so on. tools for managing your environment, including the:

    Azure portal
    Azure PowerShell
    Azure Command Line Interface (CLI)

### What is the Azure portal?
The Azure portal is a web-based, unified console that provides an alternative to command-line tools. With the Azure portal, you can manage your Azure subscription by using a graphical user interface. You can:

    1 Build, manage, and monitor everything from simple web apps to complex cloud deployments
    2 Create custom dashboards for an organized view of resources
    3 Configure accessibility options for an optimal experience

The Azure portal is designed for resiliency and continuous availability. It maintains a presence in every Azure datacenter. This configuration makes the Azure portal resilient to individual datacenter failures and avoids network slowdowns by being close to users. The Azure portal updates continuously and requires no downtime for maintenance activities.

## Azure Cloud Shell
Azure Cloud Shell is a browser-based shell tool that allows you to create, configure, and manage Azure resources using a shell. Azure Cloud Shell support both Azure PowerShell and the Azure Command Line Interface (CLI), which is a Bash shell.

Azure Cloud Shell has several features that make it a unique offering to support you in managing Azure. Some of those features are:

1.It is a browser-based shell experience, with no local installation or configuration required.

2.It is authenticated to your Azure credentials, so when you log in it inherently knows who you are and what permissions you have.

3.You choose the shell you’re most familiar with; Azure Cloud Shell supports both Azure PowerShell and the Azure CLI (which uses Bash).

### What is Azure PowerShell?
Azure PowerShell is a shell with which developers, DevOps, and IT professionals can run commands called command-lets (cmdlets). These commands call the Azure REST API to perform management tasks in Azure. Cmdlets can be run independently to handle one-off changes, or they may be combined to help orchestrate complex actions such as:

The routine setup, teardown, and maintenance of a single resource or multiple connected resources.
The deployment of an entire infrastructure, which might contain dozens or hundreds of resources, from imperative code.
Capturing the commands in a script makes the process repeatable and automatable.

In addition to be available via Azure Cloud Shell, you can install and configure Azure PowerShell on Windows, Linux, and Mac platforms.

### What is the Azure CLI?
The Azure CLI is functionally equivalent to Azure PowerShell, with the primary difference being the syntax of commands. While Azure PowerShell uses PowerShell commands, the Azure CLI uses Bash commands.

The Azure CLI provides the same benefits of handling discrete tasks or orchestrating complex operations through code. It’s also installable on Windows, Linux, and Mac platforms, as well as through Azure Cloud Shell.

Due to the similarities in capabilities and access between Azure PowerShell and the Bash based Azure CLI, it mainly comes down to which language you’re most familiar with.

# Topic 8 : Tools Used in Azure

## Describe the purpose of Azure Advisor
Azure Advisor evaluates your Azure resources and makes recommendations to help improve reliability, security, and performance, achieve operational excellence, and reduce costs

When you're in the Azure portal, the Advisor dashboard displays personalized recommendations for all your subscriptions. You can use filters to select recommendations for specific subscriptions, resource groups, or services. The recommendations are divided into five categories:

1.Reliability is used to ensure and improve the continuity of your business-critical applications.

2.Security is used to detect threats and vulnerabilities that might lead to security breaches.

3.Performance is used to improve the speed of your applications.

4.Operational Excellence is used to help you achieve process and workflow efficiency, resource manageability, and deployment best practices.

5.Cost is used to optimize and reduce your overall Azure spending.

## Describe Azure Service Health
Microsoft Azure provides a global cloud solution to help you manage your infrastructure needs, reach your customers, innovate, and adapt rapidly. Azure Service Health helps you keep track of Azure resource, both your specifically deployed resources and the overall status of Azure. Azure service health does this by combining three different Azure services:

1.Azure status informs you of service outages in Azure on the Azure Status page. The page is a global view of the health of all Azure services across all Azure regions. It’s a good reference for incidents with widespread impact.

2.Service Health provides a narrower view of Azure services and regions. It focuses on the Azure services and regions you're using. This is the best place to look for service impacting communications about outages, planned maintenance activities, and other health advisories because the authenticated Service Health experience knows which services and resources you currently use.

3.Resource Health is a tailored view of your actual Azure resources. It provides information about the health of your individual cloud resources.

By using Azure status, Service health, and Resource Health, Azure Service Health gives you a complete view of your Azure environment-all the way from the global status of Azure services and regions down to specific resources. 

## Describe Azure Monitor
Azure Monitor is a platform for collecting data on your resources, analyzing that data, visualizing the information, and even acting on the results. Azure Monitor can monitor Azure resources, your on-premises resources, and even multi-cloud resources like virtual machines hosted with a different cloud provider.

### Azure Log Analytics
Azure Log Analytics is the tool in the Azure portal where you’ll write and run log queries on the data gathered by Azure Monitor. Log Analytics is a robust tool that supports both simple, complex queries, and data analysis.Whether you work with the results of your queries interactively or use them with other Azure Monitor features such as log query alerts or workbooks, Log Analytics is the tool that you're going to use to write and test those queries.

### Azure Monitor Alerts
Azure Monitor Alerts are an automated way to stay informed when Azure Monitor detects a threshold being crossed. You set the alert conditions, the notification actions, and then Azure Monitor Alerts notifies when an alert is triggered. Depending on your configuration, Azure Monitor Alerts can also attempt corrective action.

Alerts can be set up to monitor the logs and trigger on certain log events, or they can be set to monitor metrics and trigger when certain metrics are crossed. For example, you could set a metric-based alert up to notify you when the CPU usage on a virtual machine exceeded 80%.

zure Monitor Alerts use action groups to configure who to notify and what action to take. An action group is simply a collection of notification and action preferences that you associate with one or multiple alerts.

### Application Insights
Application Insights, an Azure Monitor feature, monitors your web applications. Application Insights is capable of monitoring applications that are running in Azure, on-premises, or in a different cloud environment.

There are two ways to configure Application Insights to help monitor your application. You can either install an SDK in your application, or you can use the Application Insights agent. The Application Insights agent is supported in C#.NET, VB.NET, Java, JavaScript, Node.js, and Python.

Once Application Insights is up and running, you can use it to monitor a broad array of information, such as:

1.Request rates, response times, and failure rates

2.Dependency rates, response times, and failure rates, to show whether external services are slowing down performance

3.Page views and load performance reported by users' browsers

4.AJAX calls from web pages, including rates, response times, and failure rates

5.User and session counts
6.Performance counters from Windows or Linux server machines, such as CPU, memory, and network usage

Not only does Application Insights help you monitor the performance of your application, but you can also configure it to periodically send synthetic requests to your application, allowing you to check the status and monitor your application even during periods of low activity.

