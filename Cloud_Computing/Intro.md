# Learning objectives

## Define cloud computing.

1.Cloud computing is the delivery of computing services over the internet. Computing services include common IT infrastructure such as virtual machines, storage, databases, and networking. 

2.Cloud services also expand the traditional IT offerings to include things like Internet of Things (IoT), machine learning (ML), and artificial intelligence (AI).


3.Because cloud computing uses the internet to deliver these services, it doesn’t have to be constrained by physical infrastructure the same way that a traditional datacenter is. That means if you need to increase your IT infrastructure rapidly, you don’t have to wait to build a new datacenter—you can use the cloud to rapidly expand your IT footprint.


## Describe the shared responsibility model.

Start with a traditional corporate datacenter. The company is responsible for maintaining the physical space, ensuring security, and maintaining or replacing the servers if anything happens. The IT department is responsible for maintaining all the infrastructure and software needed to keep the datacenter up and running. They’re also likely to be responsible for keeping all systems patched and on the correct version.

1. With the shared responsibility model, these responsibilities get shared between the cloud provider and the consumer.
2. Physical security, power, cooling, and network connectivity are the responsibility of the CLOUD PROVIDER .
 The consumer isn’t collocated with the datacenter, so it wouldn’t make sense for the consumer to have any of those responsibilities.

3.the CONSUMER is responsible for the data and information stored in the cloud. (You wouldn’t want the cloud provider to be able to read your information.) The consumer is also responsible for access security, meaning you only give access to those who need it.

for some things, the responsibility depends on the situation. If you’re using a cloud SQL database, the CLOUD PROVIDER would be responsible for maintaining the actual database. However, you’re still responsible for the data that gets ingested into the database. If you deployed a virtual machine and installed an SQL database on it, you’d be responsible for database patches and updates, as well as maintaining the data and information stored in the database.


With an on-premises datacenter, you’re responsible for everything. With cloud computing, those responsibilities shift

The shared responsibility model is heavily tied into the cloud service types (covered later in this learning path):

    1.infrastructure as a service (IaaS) - IaaS places the most responsibility on the consumer, with the cloud provider being responsible for the basics of physical security, power, and connectivity.

    2.platform as a service (PaaS) - PaaS, being a middle ground between IaaS and SaaS, rests somewhere in the middle and evenly distributes responsibility between the cloud provider and the consumer.

    3.software as a service (SaaS) - SaaS places most of the responsibility with the cloud provider.


    Image link : https://learn.microsoft.com/en-us/training/wwl-azure/describe-cloud-compute/media/shared-responsibility-b3829bfe.svg

-->When using a cloud provider, you’ll always be responsible for:

1.The information and data stored in the cloud
2.Devices that are allowed to connect to your cloud (cell phones, computers, and so on)
3.The accounts and identities of the people, services, and devices within your organization


-->The cloud provider is always responsible for:

1.The physical datacenter
2.The physical network
3.The physical hosts


-->Your service model will determine responsibility for things like:

1.Operating systems
2.Network controls
3.Applications
4.Identity and infrastructure



##Define cloud models, including public, private, and hybrid.

What are cloud models? The cloud models define the deployment type of cloud resources. 
The three main cloud models are: 
        private, public, and hybrid.

1.PRIVATE CLOUD

Let’s start with a private cloud. A private cloud is, in some ways, the natural evolution from a corporate datacenter. It’s a cloud (delivering IT services over the internet) that’s used by a single entity. Private cloud provides much greater control for the company and its IT department. However, it also comes with greater cost and fewer of the benefits of a public cloud deployment. Finally, a private cloud may be hosted from your on site datacenter. It may also be hosted in a dedicated datacenter offsite, potentially even by a third party that has dedicated that datacenter to your company.

2.Public cloud

A public cloud is built, controlled, and maintained by a third-party cloud provider. With a public cloud, anyone that wants to purchase cloud services can access and use resources. The general public availability is a key difference between public and private clouds.

3.Hybrid cloud

A hybrid cloud is a computing environment that uses both public and private clouds in an inter-connected environment. A hybrid cloud environment can be used to allow a private cloud to surge for increased, temporary demand by deploying public cloud resources. Hybrid cloud can be used to provide an extra layer of security. For example, users can flexibly choose which services to keep in public cloud and which to deploy to their private cloud infrastructure.

4.Multi-cloud

A fourth, and increasingly likely scenario is a multi-cloud scenario. In a multi-cloud scenario, you use multiple public cloud providers. Maybe you use different features from different cloud providers. Or maybe you started your cloud journey with one provider and are in the process of migrating to a different provider. Regardless, in a multi-cloud environment you deal with two (or more) public cloud providers and manage resources and security in both environments.

5.Azure Arc

Azure Arc is a set of technologies that helps manage your cloud environment. Azure Arc can help manage your cloud environment, whether it's a public cloud solely on Azure, a private cloud in your datacenter, a hybrid configuration, or even a multi-cloud environment running on multiple cloud providers at once.

6.Azure VMware Solution

What if you’re already established with VMware in a private cloud environment but want to migrate to a public or hybrid cloud? Azure VMware Solution lets you run your VMware workloads in Azure with seamless integration and scalability.



##Identify appropriate use cases for each cloud model.

##Describe the consumption-based model.

##Compare cloud pricing models.