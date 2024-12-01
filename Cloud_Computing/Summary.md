# Cloud computing

1.Cloud computing is the delivery of computing services over the internet. Computing services include common IT infrastructure such as virtual machines, storage, databases, and networking. 

2.Cloud services also provides other IT offerings like Internet of Things (IoT), machine learning (ML), and artificial intelligence (AI).

3.In this we can transfer services through internet.we don't have to wait for datacenter to build as we can rapidly expand our IT infrastructure using cloud services.

## Shared responsibility model.

In traditional corporate datacenter, the It dept. of any company is responsible for maintaining the physical space, ensuring security, and maintaining or replacing the servers if anything happens They’re also responsible for keeping all systems patched and on the correct version.

With the shared responsibility model, these responsibilities get shared between the cloud provider and the consumer.
1.Physical security, power, cooling, and network connectivity are the responsibility of the CLOUD PROVIDER .

2.the CONSUMER is responsible for the data and information stored in the cloud. The consumer is also responsible for access security, meaning you only give access to those who need it.

The consumer isn’t collocated with the datacenter and you(consumer) wouldn’t want the cloud provider to be able to read your information.

for some things, the responsibility depends on the situation. If you(consumer) using a cloud SQL database, the CLOUD PROVIDER would be responsible for maintaining the actual database.However, consumer is still responsible for the data that gets ingested into the database. **but** If you deploy a virtual machine and installed an SQL database on it, you’d be responsible for database patches, updates,maintaining the data and information stored in the database.

The shared responsibility model is heavily tied into the cloud service types:

    1.infrastructure as a service (IaaS) most responsibility on the consumer, with the cloud provider being responsible for the basics of physical security, power, and connectivity.
    2.platform as a service (PaaS) being a middle ground between IaaS and SaaS, rests somewhere in the middle and evenly distributes responsibility between the cloud provider and the consumer.
    3.software as a service (SaaS) - SaaS places most of the responsibility with the cloud provider.

As a consumer you will be responsible for:

    1.The information and data stored in the cloud
    2.Devices that are allowed to connect to your cloud (cell phones, computers, and so on)
    3.The accounts and identities of the people, services, and devices within your organization

The cloud provider is always responsible for:

    1.The physical datacenter
    2.The physical network  
    3.The physical hosts

Your service model will determine responsibility for things like:

1.Operating systems
2.Network controls
3.Applications
4.Identity and infrastructure

## Define cloud Models

The three main cloud models are: 

        private, public, and hybrid.

Private

A private cloud is the natural evolution from a corporate datacenter.It's a cloud that’s used by a single entity. Private cloud provides much greater control for the company and its IT department.high cost and less public benefits.Can be hosted from site datacenter,dedicated offsite datacenter.

Public

A public cloud is built, controlled, and maintained by a third-party cloud provider. With a public cloud, anyone that wants to purchase cloud services can access and use resources.

Hybrid

A hybrid cloud is a computing environment that uses both public and private clouds in an inter-connected environment. A hybrid cloud environment can be used to allow a private cloud to surge for increased, temporary demand by deploying public cloud resources. Hybrid cloud can be used to provide an extra layer of security.

Multicloud

in a multi-cloud environment you deal with two (or more) public cloud providers and manage resources and security in both environments. or use different features from different cloud.

Azure Arc

Azure Arc is a set of technologies that helps manage your cloud environment. Azure Arc can help manage your cloud environment, whether it's a public cloud solely on Azure, a private cloud in your datacenter, a hybrid configuration, or even a multi-cloud environment running on multiple cloud providers at once.

Azure VMware Solution

What if you’re already established with VMware in a private cloud environment but want to migrate to a public or hybrid cloud? Azure VMware Solution lets you run your VMware workloads in Azure with seamless integration and scalability.

## Uses of cloud computing

Disaster recovery:Cloud infrastructure can help with data recovery and business continuity in the event of a disaster. 

Storage: Cloud storage can store large amounts of data and is becoming the new standard for IT solutions. 

Test and development: The cloud's flexibility allows for quick environment creation, testing, and destruction. 

Application migration: Hybrid clouds can provide secure landing zones for migrating applications. 

Artificial intelligence as a service: Cloud-hosted AI libraries, modeling engines, and algorithms can be crucial for adopting AI. 

Cost saving: IaaS (Infrastructure as a Service) helps reduce upfront capital expenditures by allowing users to pay for only the resources they consume. 

Production workload hosting: The public cloud can be used to host live production workloads. 

Uncertain and excessive cloud costs: Clouds are more like utilities, with pay-per-use cost models that can result in different costs to operate a workload. 

## Consumption base model

there are two types of expenses to consider. Capital expenditure (CapEx) and operational expenditure (OpEx).

*CapEx* is typically a one-time, up-front expenditure to purchase or secure tangible resources. A new building, repaving the parking lot, building a datacenter, or buying a company vehicle are examples of CapEx.

*OpEx* is spending money on services or products over time. Renting a convention center, leasing a company vehicle, or signing up for cloud services are all examples of OpEx.

Cloud computing falls under **OpEx** because cloud computing operates on a consumption-based model.you pay for the IT resources you use. If you don’t use any IT resources this month, you don’t pay for any IT resources.

This consumption-based model has many benefits, including:

1.No upfront costs.
2.No need to purchase and manage costly infrastructure that users might not use.
3.The ability to pay for more resources when they're needed.
4.The ability to stop paying for resources that are no longer needed.

## cloud pricing model

Cloud computing is the delivery of computing services over the internet by using a pay-as-you-go pricing model. You typically pay only for the cloud services you use, which helps you:

1.Plan and manage your operating costs.
2.Run your infrastructure more efficiently.
3.Scale as your business needs change.

# Benefits

two of the biggest considerations are uptime (or availability) and the ability to handle demand (or scale).

## High availability

When you’re deploying an application, service, or any IT resources, it’s important that  the resources are available when needed. High availability focuses on ensuring maximum availability.regardless of any disruptions.
When you’re architecting your solution, you’ll need to account for service availability guarantees,Azure provides uptime guarantees depending on the service. These guarantees are part of the service-level agreements (SLAs).

## Scalability

Scalability refers to the ability to adjust resources to meet demand. If you suddenly experience peak traffic and your systems are overwhelmed, the ability to scale means you can add more resources to handle the increased demand.
The other benefit of scalability is that you aren't overpaying for services.you pay for what you use 

### Scaling generally comes in two varieties

**Horizontal** scaling is adding or subtracting the number of resources.
**Vertical** scaling is focused on increasing or decreasing the capabilities of resources.


## benefits of reliability and predictability in the cloud.

Reliability is the ability of a system to recover from failures and continue to function

Predictability in the cloud lets you move forward with confidence. Predictability can be focused on PERFORMANCE predictability or COST predictability.

**Performance** - Performance predictability focuses on predicting the resources needed to deliver a positive experience for your customers. Autoscaling, load balancing, and high availability are just some of the cloud concepts that support performance predictability

**Cost** - Cost predictability is focused on predicting or forecasting the cost of the cloud spend. With the cloud, you can track your resource use in real time.By using cloud analytics and information, you can predict future costs and adjust your resources as needed. You can even use tools like the Total Cost of Ownership (TCO) or Pricing Calculator to get an estimate of potential cloud spend.

## benefits of security and governance in the cloud.

IAAS and PAAS both provide cloud features support governance and compliance. Things like set templates help ensure that all your deployed resources meet corporate standards and government regulatory requirements. Plus, you can update all your deployed resources to new standards as standards change.Depending on your operating model, software patches and updates may also automatically be applied, which helps with both governance and security.

On the security side, you can find a cloud solution that matches your security needs. If you want maximum control of security, infrastructure as a service(IAAS) provides you with physical resources but lets you manage the operating systems and installed software, including patches and maintenance. If you want patches and maintenance taken care of automatically, platform as a service(PAAS) or software as a service(SAAS) deployments may be the best cloud strategies for you.

nd because the cloud is intended as an over-the-internet delivery of IT resources, cloud providers are typically well suited to handle things like distributed denial of service (DDoS) attacks, making your network more robust and secure.

## benefits of manageability in the cloud.

Management of the cloud speaks to managing your cloud resources. In the cloud, you can:

1.Automatically scale resource deployment based on need.
2.Deploy resources based on a preconfigured template, removing the need for manual configuration.
3.Monitor the health of resources and automatically replace failing resources.
4.Receive automatic alerts based on configured metrics, so you’re aware of performance in real time.

## Management in the cloud

Management in the cloud speaks to how you’re able to manage your cloud environment and resources. You can manage these:

1.Through a web portal.
2.Using a command line interface.
3.Using APIs.
4.Using PowerShell.

# Types

## Infrastructure as a Service (IaaS). 

Infrastructure as a service (IaaS) is the most flexible category of cloud services, as it provides you the maximum amount of control for your cloud resources.
In an IaaS model, the cloud provider is responsible for maintaining the hardware, network connectivity (to the internet), and physical security. You’re responsible for everything else: like operating system installation, configuration, and maintenance; network configuration; database and storage configuration.

IaaS places the largest share of responsibility with you. The cloud provider is responsible for maintaining the physical infrastructure and its access to the internet. You’re responsible for installation and configuration, patching and updates, and security.

### Some scenerios:

1.lift-and-shift migration: You’re setting up cloud resources similar to your on-prem datacenter, and then simply moving the things running on-prem to running on the IaaS infrastructure.

Testing and development: You have established configurations for development and test environments that you need to rapidly replicate. You can start up or shut down the different environments rapidly with an IaaS structure, with complete control.

### Use cases for IAAS

    1 Test and Development: Quickly setting up and dismantling test and development environments.
    2 Website Hosting: Hosting websites on IaaS is flexible and cost-effective.
    3 Storage, Backup, and Recovery: IaaS provides manageable, scalable storage options with a pay-as-you-go model, ideal for backup and recovery solutions.
    4 High-Performance Computing: By using advanced configurations, IaaS can support high-performance computing for complex tasks like simulations and analysis.
    5 Big Data Analysis: IaaS provides the necessary computing power and storage to perform big data analytics.

## PAAS(platform as a service)

Platform as a service (PaaS) is a middle ground between renting space in a datacenter (infrastructure as a service) and paying for a complete and deployed solution (software as a service). In a PaaS environment, the cloud provider maintains the physical infrastructure, physical security, and connection to the internet. They also maintain the operating systems, development tools, and business intelligence services that make up a cloud solution. In a PaaS, you don't have to worry about the licensing or patching for operating systems and databases.

PaaS is well suited to provide a complete development environment without maintaining all the development infrastructure. PaaS splits the responsibility between you and the cloud provider. Depending on the configuration, you or the cloud provider may be responsible for networking settings and connectivity within your cloud environment, network and application security, and the directory infrastructure.


### Scenerio

Development framework: PaaS provides a framework that developers can build upon to develop or customize cloud-based applications.PaaS lets developers create applications using built-in software components.Cloud features such as scalability, high-availability,reducing the amount of coding that developers must do.

Analytics or business intelligence: Tools provided as a service with PaaS allow organizations to analyze and mine their data, finding insights and patterns and predicting outcomes to improve forecasting, product design decisions, investment returns, and other business decisions.

**Use Cases**

    1. Application Development: Streamlining the development process with a pre-configured platform, which can considerably reduce coding time.
    2. API Development and Management: Creating and managing APIs easily without worrying about the underlying infrastructure.
    3. Business Analytics/BI Tools: Implementing complex business analytics and intelligence solutions with built-in data storage and processing services.
    4. Additional Features Integration: Easily integrating with additional services provided by Azure to enhance application capabilities.
    5. Internet of Things (IoT): Developing IoT applications with built-in services designed specifically for handling and analyzing IoT data streams.

## SAAS (Software as a service)


