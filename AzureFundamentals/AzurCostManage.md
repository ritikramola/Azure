# Introduction

In this module, you’ll be introduced to factors that impact costs in Azure and tools to help you both predict potential costs and monitor and control costs.

## Describe factors that can affect costs in Azure

link: https://www.microsoft.com/en-us/videoplayer/embed/RWGNx4?postJsllMsg=true

Azure shifts development costs from the capital expense (CapEx) of building out and maintaining infrastructure and facilities to an operational expense (OpEx) of renting infrastructure as you need it, whether it’s compute, storage, networking, and so on.

That OpEx cost can be impacted by many factors. Some of the impacting factors are:

    Resource type
    Consumption 
    Maintenance
    Geography   
    Subscription type
    Azure Marketplace

### Resource type
A number of factors influence the cost of Azure resources. The type of resources, the settings for the resource, and the Azure region will all have an impact on how much a resource costs. When you provision an Azure resource, Azure creates metered instances for that resource. The meters track the resources' usage and generate a usage record that is used to calculate your bill.

**Example**
With a storage account, you specify a type such as blob, a performance tier, an access tier, redundancy settings, and a region. Creating the same storage account in different regions may show different costs and changing any of the settings may also impact the price.

Screenshot of storage blob settings showing hot and cool access tiers.

With a virtual machine (VM), you may have to consider licensing for the operating system or other software, the processor and number of cores for the VM, the attached storage, and the network interface. Just like with storage, provisioning the same virtual machine in different regions may result in different costs.

### Consumption

Pay-as-you-go has been a consistent theme throughout, and that’s the cloud payment model where you pay for the resources that you use during a billing cycle. If you use more compute this cycle, you pay more. If you use less in the current cycle, you pay less. It’s a straight forward pricing mechanism that allows for maximum flexibility.

However, Azure also offers the ability to commit to using a set amount of cloud resources in advance and receiving discounts on those “reserved” resources. Many services, including databases, compute, and storage all provide the option to commit to a level of use and receive a discount, in some cases up to 72 percent.

When you reserve capacity, you’re committing to using and paying for a certain amount of Azure resources during a given period (typically one or three years). With the back-up of pay-as-you-go, if you see a sudden surge in demand that eclipses what you’ve pre-reserved, you just pay for the additional resources in excess of your reservation. This model allows you to recognize significant savings on reliable, consistent workloads while also having the flexibility to rapidly increase your cloud footprint as the need arises.

### Maintenance

The flexibility of the cloud makes it possible to rapidly adjust resources based on demand. Using resource groups can help keep all of your resources organized. In order to control costs, it’s important to maintain your cloud environment. For example, every time you provision a VM, additional resources such as storage and networking are also provisioned. If you deprovision the VM, those additional resources may not deprovision at the same time, either intentionally or unintentionally. By keeping an eye on your resources and making sure you’re not keeping around resources that are no longer needed, you can help control cloud costs.

### Geography

When you provision most resources in Azure, you need to define a region where the resource deploys. Azure infrastructure is distributed globally, which enables you to deploy your services centrally or closest to your customers, or something in between. With this global deployment comes global pricing differences. The cost of power, labor, taxes, and fees vary depending on the location. Due to these variations, Azure resources can differ in costs to deploy depending on the region.

Network traffic is also impacted based on geography. For example, it’s less expensive to move information within Europe than to move information from Europe to Asia or South America.

### Network Traffic

Billing zones are a factor in determining the cost of some Azure services.

Bandwidth refers to data moving in and out of Azure datacenters. Some inbound data transfers (data going into Azure datacenters) are free. For outbound data transfers (data leaving Azure datacenters), data transfer pricing is based on zones.

A zone is a geographical grouping of Azure regions for billing purposes. The bandwidth pricing page has additional information on pricing for data ingress, egress, and transfer.

### Subscription type

Some Azure subscription types also include usage allowances, which affect costs.

For example, an Azure free trial subscription provides access to a number of Azure products that are free for 12 months. It also includes credit to spend within your first 30 days of sign-up. You'll get access to more than 25 products that are always free (based on resource and region availability).

### Azure Marketplace

Azure Marketplace lets you purchase Azure-based solutions and services from third-party vendors. This could be a server with software preinstalled and configured, or managed network firewall appliances, or connectors to third-party backup services. When you purchase products through Azure Marketplace, you may pay for not only the Azure services that you’re using, but also the services or expertise of the third-party vendor. Billing structures are set by the vendor.

All solutions available in Azure Marketplace are certified and compliant with Azure policies and standards. The certification policies may vary based on the service or solution type and Azure service involved. Commercial marketplace certification policies has additional information on Azure Marketplace certifications.

## Compare the Pricing and Total Cost of Ownership calculators

The pricing calculator and the total cost of ownership (TCO) calculator are two calculators that help you understand potential Azure expenses. Both calculators are accessible from the internet, and both calculators allow you to build out a configuration. However, the two calculators have very different purposes.

### Pricing calculator

The pricing calculator is designed to give you an estimated cost for provisioning resources in Azure. You can get an estimate for individual resources, build out a solution, or use an example scenario to see an estimate of the Azure spend. The pricing calculator’s focus is on the cost of provisioned resources in Azure.

 **Note**

The Pricing calculator is for information purposes only. The prices are only an estimate. Nothing is provisioned when you add resources to the pricing calculator, and you won't be charged for any services you select.

With the pricing calculator, you can estimate the cost of any provisioned resources, including compute, storage, and associated network costs. You can even account for different storage options like storage type, access tier, and redundancy.

image:https://learn.microsoft.com/en-us/training/wwl-azure/describe-cost-management-azure/media/price-calculator-0a750ac3.png

### TCO calculator

The TCO calculator is designed to help you compare the costs for running an on-premises infrastructure compared to an Azure Cloud infrastructure. With the TCO calculator, you enter your current infrastructure configuration, including servers, databases, storage, and outbound network traffic. The TCO calculator then compares the anticipated costs for your current environment with an Azure environment supporting the same infrastructure requirements.

With the TCO calculator, you enter your configuration, add in assumptions like power and IT labor costs, and are presented with an estimation of the cost difference to run the same environment in your current datacenter or in Azure.


image:https://learn.microsoft.com/en-us/training/wwl-azure/describe-cost-management-azure/media/total-cost-ownership-657fe344.png


## Exercise - Estimate workload costs by using the Pricing calculator

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

Explore the Pricing calculator
Let's start with a quick tour of the Pricing calculator.

Go to the Pricing calculator.

Notice the following tabs:

link:https://learn.microsoft.com/en-us/training/wwl-azure/describe-cost-management-azure/media/price-calculator-menu-bar-4a43e988.png

Products This is where you choose the Azure services that you want to include in your estimate. You'll likely spend most of your time here.

Example scenarios Here you'll find several reference architectures, or common cloud-based solutions that you can use as a starting point.

Saved estimates Here you'll find your previously saved estimates.

FAQs Here you'll discover answers to frequently asked questions about the Pricing calculator.

### Estimate your solution

#### Add services to the estimate

On the Products tab, select the service from each of these categories:

    Category	Service

Compute	Virtual Machines

Databases	Azure SQL Database

Networking	Application Gateway

Scroll to the bottom of the page. Each service is listed with its default configuration.

### Review, share, and save your estimate

At the bottom of the page, you see the total estimated cost of running the solution. You can change the currency type if you want.

At this point, you have a few options:

Select Export to save your estimate as an Excel document.
Select Save or Save as to save your estimate to the Saved Estimates tab for later.
Select Share to generate a URL so you can share the estimate with your team.

## Exercise - Compare workload costs using the TCO calculator

In this exercise, you use the Total Cost of Ownership (TCO) Calculator to compare the cost of running a sample workload in your datacenter versus on Azure.

Assume you're considering moving some of your on-premises workloads to the cloud. But first, you need to understand more about moving from a relatively fixed cost structure to an ongoing monthly cost structure.

You'll need to investigate whether there are any potential cost savings in moving your datacenter to the cloud over the next three years. You need to take into account all of the potentially hidden costs involved with operating on-premises and in the cloud.

Instead of manually collecting everything you think might be included, you use the TCO Calculator as a starting point. You adjust the provided cost assumptions to match your on-premises environment.

### Recall that the TCO Calculator involves three steps:

link:https://learn.microsoft.com/en-us/training/wwl-azure/describe-cost-management-azure/media/total-cost-ownership-calculator-steps-76e927a5.png

#### Define your workloads

1.Enter the specifications of your on-premises infrastructure into the TCO Calculator.
2.Go to the TCO Calculator.
3.Under Define your workloads, select Add server workload to create a row for your bank of Windows Server VMs.
4.Select Add server workload to create a second row for your bank of Linux VMs.
5.Under Storage, select Add storage.
6.Under Networking, set Outbound bandwidth to 15 TB.
7.Select Next.

#### Adjust assumptions

Here, you specify your currency. For brevity, you leave the remaining fields at their default values.

In practice, you would adjust any cost assumptions and make any adjustments to match your current on-premises environment.

    At the top of the page, select your currency. This example uses US Dollar ($).  
    Select Next.

#### View the report

Take a moment to review the generated report.

Remember, you've been tasked to investigate cost savings for your European datacenter over the next three years.

To make these adjustments:

    Set Timeframe to 3 Years.
    Set Region to North Europe.

Great work. You now have the information that you can share with your Chief Financial Officer. If you need to make adjustments, you can revisit the TCO Calculator to generate a fresh report.


## Describe the Microsoft Cost Management tool

Microsoft Azure is a global cloud provider, meaning you can provision resources anywhere in the world. You can provision resources rapidly to meet a sudden demand, or to test out a new feature, or on accident. If you accidentally provision new resources, you may not be aware of them until it’s time for your invoice. Cost Management is a service that helps avoid those situations.

### What is Cost Management?

Cost Management provides the ability to quickly check Azure resource costs, create alerts based on resource spend, and create budgets that can be used to automate management of resources.

Cost analysis is a subset of Cost Management that provides a quick visual for your Azure costs. Using cost analysis, you can quickly view the total cost in a variety of different ways, including by billing cycle, region, resource, and so on.

image:https://learn.microsoft.com/en-us/training/wwl-azure/describe-cost-management-azure/media/cost-analysis-b52dedab.png

You use cost analysis to explore and analyze your organizational costs. You can view aggregated costs by organization to understand where costs are accrued and to identify spending trends. And you can see accumulated costs over time to estimate monthly, quarterly, or even yearly cost trends against a budget.


### Cost alerts

Cost alerts provide a single location to quickly check on all of the different alert types that may show up in the Cost Management service. The three types of alerts that may show up are:

    Budget alerts
    Credit alerts
    Department spending quota alerts.

#### Budget alerts

Budget alerts notify you when spending, based on usage or cost, reaches or exceeds the amount defined in the alert condition of the budget. Cost Management budgets are created using the Azure portal or the Azure Consumption API.

In the Azure portal, budgets are defined by cost. Budgets are defined by cost or by consumption usage when using the Azure Consumption API. Budget alerts support both cost-based and usage-based budgets. Budget alerts are generated automatically whenever the budget alert conditions are met. You can view all cost alerts in the Azure portal. Whenever an alert is generated, it appears in cost alerts. An alert email is also sent to the people in the alert recipients list of the budget.

#### Credit alerts

Credit alerts notify you when your Azure credit monetary commitments are consumed. Monetary commitments are for organizations with Enterprise Agreements (EAs). Credit alerts are generated automatically at 90% and at 100% of your Azure credit balance. Whenever an alert is generated, it's reflected in cost alerts, and in the email sent to the account owners.

#### Department spending quota alerts

Department spending quota alerts notify you when department spending reaches a fixed threshold of the quota. Spending quotas are configured in the EA portal. Whenever a threshold is met, it generates an email to department owners, and appears in cost alerts. For example, 50 percent or 75 percent of the quota.

### Budgets

A budget is where you set a spending limit for Azure. You can set budgets based on a subscription, resource group, service type, or other criteria. When you set a budget, you will also set a budget alert. When the budget hits the budget alert level, it will trigger a budget alert that shows up in the cost alerts area. If configured, budget alerts will also send an email notification that a budget alert threshold has been triggered.

A more advanced use of budgets enables budget conditions to trigger automation that suspends or otherwise modifies resources once the trigger condition has occurred.

## Describe the purpose of tags

As your cloud usage grows, it's increasingly important to stay organized. A good organization strategy helps you understand your cloud usage and can help you manage costs.

One way to organize related resources is to place them in their own subscriptions. You can also use resource groups to manage related resources. Resource tags are another way to organize resources. Tags provide extra information, or metadata, about your resources. This metadata is useful for:

1.Resource management Tags enable you to locate and act on resources that are associated with specific workloads, environments, business units, and owners.

2.Cost management and optimization Tags enable you to group resources so that you can report on costs, allocate internal cost centers, track budgets, and forecast estimated cost.

3.Operations management Tags enable you to group resources according to how critical their availability is to your business. This grouping helps you formulate service-level agreements (SLAs). An SLA is an uptime or performance guarantee between you and your users.

4.Security Tags enable you to classify data by its security level, such as public or confidential.

5.Governance and regulatory compliance Tags enable you to identify resources that align with governance or regulatory compliance requirements, such as ISO 27001. Tags can also be part of your standards enforcement efforts. For example, you might require that all resources be tagged with an owner or department name.

6.Workload optimization and automation Tags can help you visualize all of the resources that participate in complex deployments. For example, you might tag a resource with its associated workload or application name and use software such as Azure DevOps to perform automated tasks on those resources.

### How do I manage resource tags?

You can add, modify, or delete resource tags through Windows PowerShell, the Azure CLI, Azure Resource Manager templates, the REST API, or the Azure portal.

You can use Azure Policy to enforce tagging rules and conventions. For example, you can require that certain tags be added to new resources as they're provisioned. You can also define rules that reapply tags that have been removed. Resources don't inherit tags from subscriptions and resource groups, meaning that you can apply tags at one level and not have those tags automatically show up at a different level, allowing you to create custom tagging schemas that change depending on the level (resource, resource group, subscription, and so on).


#### An example tagging structure

A resource tag consists of a name and a value. You can assign one or more tags to each Azure resource.

Name	  Value

AppName	    The name of the application that the resource is part of.

CostCenter	    The internal cost center code.

Owner	        The name of the business owner who's responsible for the resource.

Environment	    An environment name, such as "Prod," "Dev," or "Test."

Impact	    How important the resource is to business operations, such as "Mission-critical," "High-impact,"        
            or  "Low-impact."


