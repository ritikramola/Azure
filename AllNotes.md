**Azure Arc** can help manage your cloud environment

## How to work in Sandbox

    1. Powershell
    2.Bash CLI
    3.Use Azure CLI interactive mode

## TWO IMPORTANT PILLAR

    Physical Infrastructure pillar and Management Infrastructure pillar

### Physical Infrastructure Pillar

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

