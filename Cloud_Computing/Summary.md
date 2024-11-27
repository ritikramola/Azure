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

