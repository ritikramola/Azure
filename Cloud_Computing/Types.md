# Learning Objectives

## Describe infrastructure as a service (IaaS).

Infrastructure as a service (IaaS) is the most flexible category of cloud services, as it provides you the maximum amount of control for your cloud resources. In an IaaS model, the cloud provider is responsible for maintaining the hardware, network connectivity (to the internet), and physical security. You’re responsible for everything else: operating system installation, configuration, and maintenance; network configuration; database and storage configuration; and so on. With IaaS, you’re essentially renting the hardware in a cloud datacenter, but what you do with that hardware is up to you.

### Shared responsibility model

The shared responsibility model applies to all the cloud service types. IaaS places the largest share of responsibility with you. The cloud provider is responsible for maintaining the physical infrastructure and its access to the internet. You’re responsible for installation and configuration, patching and updates, and security.

Image link : https://learn.microsoft.com/en-us/training/wwl-azure/describe-cloud-service-types/media/shared-responsibility-b3829bfe.svg

### Scenerios

Some common scenarios where IaaS might make sense include:

Lift-and-shift migration: You’re setting up cloud resources similar to your on-prem datacenter, and then simply moving the things running on-prem to running on the IaaS infrastructure.

Testing and development: You have established configurations for development and test environments that you need to rapidly replicate. You can start up or shut down the different environments rapidly with an IaaS structure, while maintaining complete control.


## Describe platform as a service (PaaS).

Platform as a service (PaaS) is a middle ground between renting space in a datacenter (infrastructure as a service) and paying for a complete and deployed solution (software as a service). In a PaaS environment, the cloud provider maintains the physical infrastructure, physical security, and connection to the internet. They also maintain the operating systems, middleware, development tools, and business intelligence services that make up a cloud solution. In a PaaS scenario, you don't have to worry about the licensing or patching for operating systems and databases.

PaaS is well suited to provide a complete development environment without the headache of maintaining all the development infrastructure.


### Shared responsibility model

The shared responsibility model applies to all the cloud service types. PaaS splits the responsibility between you and the cloud provider. The cloud provider is responsible for maintaining the physical infrastructure and its access to the internet, just like in IaaS. In the PaaS model, the cloud provider will also maintain the operating systems, databases, and development tools. Think of PaaS like using a domain joined machine: IT maintains the device with regular updates, patches, and refreshes.

Depending on the configuration, you or the cloud provider may be responsible for networking settings and connectivity within your cloud environment, network and application security, and the directory infrastructure.

image link: https://learn.microsoft.com/en-us/training/wwl-azure/describe-cloud-service-types/media/shared-responsibility-b3829bfe.svg


### Scenarios

Some common scenarios where PaaS might make sense include:

Development framework: PaaS provides a framework that developers can build upon to develop or customize cloud-based applications. Similar to the way you create an Excel macro, PaaS lets developers create applications using built-in software components. Cloud features such as scalability, high-availability, and multi-tenant capability are included, reducing the amount of coding that developers must do.

Analytics or business intelligence: Tools provided as a service with PaaS allow organizations to analyze and mine their data, finding insights and patterns and predicting outcomes to improve forecasting, product design decisions, investment returns, and other business decisions.


## Describe software as a service (SaaS).

Software as a service (SaaS) is the most complete cloud service model from a product perspective. With SaaS, you’re essentially renting or using a fully developed application. Email, financial software, messaging applications, and connectivity software are all common examples of a SaaS implementation.

While the SaaS model may be the least flexible, it’s also the easiest to get up and running. It requires the least amount of technical knowledge or expertise to fully employ.


### Shared responsibility model


The shared responsibility model applies to all the cloud service types. SaaS is the model that places the most responsibility with the cloud provider and the least responsibility with the user. In a SaaS environment you’re responsible for the data that you put into the system, the devices that you allow to connect to the system, and the users that have access. Nearly everything else falls to the cloud provider. The cloud provider is responsible for physical security of the datacenters, power, network connectivity, and application development and patching.

image link: https://learn.microsoft.com/en-us/training/wwl-azure/describe-cloud-service-types/media/shared-responsibility-b3829bfe.svg


### Scenarios

Some common scenarios for SaaS are:

Email and messaging.
Business productivity applications.
Finance and expense tracking.


## Identify appropriate use cases for each cloud service (IaaS, PaaS, SaaS).

Infrastructure as a Service (IaaS)


The most flexible cloud computing model, IaaS provides virtualized physical computing resources over the Internet. Azure’s IaaS solutions, like Azure Virtual Machines and Azure Virtual Network, offer a fully outsourced infrastructure that includes servers, storage, and networking components.

Appropriate Use Cases for IaaS:

Test and Development: Quickly setting up and dismantling test and development environments, offering a cost-effective, scalable solution.
Website Hosting: Hosting websites on IaaS can be more flexible and cost-effective than traditional web hosting.
Storage, Backup, and Recovery: IaaS provides manageable, scalable storage options with a pay-as-you-go model, ideal for backup and recovery solutions.
High-Performance Computing: By using advanced configurations, IaaS can support high-performance computing for complex tasks like simulations and analysis.
Big Data Analysis: IaaS provides the necessary computing power and storage to perform big data analytics, which might require processing a large set of data.


Platform as a Service (PaaS)

PaaS delivers a framework for developers to build upon and create customized applications. Azure’s PaaS offerings, like Azure Web Apps and Azure SQL Database, include operating systems, middleware, and runtime environments.

Appropriate Use Cases for PaaS:

Application Development: Streamlining the development process with a pre-configured platform, which can considerably reduce coding time.
API Development and Management: Creating and managing APIs easily without worrying about the underlying infrastructure.
Business Analytics/BI Tools: Implementing complex business analytics and intelligence solutions with built-in data storage and processing services.
Additional Features Integration: Easily integrating with additional services provided by Azure to enhance application capabilities.
Internet of Things (IoT): Developing IoT applications with built-in services designed specifically for handling and analyzing IoT data streams.


Software as a Service (SaaS)


SaaS provides a complete software solution which consumers can purchase on a pay-as-you go basis from a cloud service provider. Azure’s SaaS solutions include Microsoft Office 365, Dynamics 365, and various third-party applications available through the Azure Marketplace.

Appropriate Use Cases for SaaS:

Email Services: Outsource the complexity of email service setup and administration with services like Microsoft Exchange Online.
Collaboration and Communication: Utilize platforms like Microsoft Teams for advanced communication solutions without the complexity of in-house deployment and maintenance.
Customer Relationship Management (CRM): Platforms like Dynamics 365 offer CRM services directly from the cloud, updated and maintained by the service provider.
Human Resources Management (HRM): Online HRM solutions simplify the management of employee data, payroll, and recruitment processes.
Enterprise Resource Planning (ERP): Cloud-based ERP systems can help organizations to integrate and manage finance, procurement, supply chain, and other business processes.