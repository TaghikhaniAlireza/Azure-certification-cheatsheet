# Describe the Core Architectural Components of Azure

## What does Azure offer?
- Build intelligent apps and solutions with advanced technology, tools, and services to take your business to the next level.
- Seamlessly unify your technology to simplify platform management and to deliver innovations efficiently and securely on a trusted cloud.

## Explore the Learn sandbox
- `Get-date`
- `date`
- `az version`
  - Azure command to check what version of the CLI you're using right now
- `az upgrade`
  - Try to run an update to the CLI
- `az interactive`
  - Enter az interactive to enter interactive mode.

## Describe Azure physical infrastructure

### Physical infrastructure
- The physical infrastructure for Azure starts with datacenters.

### Regions
- A region is a geographical area on the planet that contains at least one, but potentially multiple datacenters that are nearby and networked together with a low-latency network.

### Availability Zones
- Availability zones are physically separate datacenters within an Azure region.
- Each availability zone is made up of one or more datacenters equipped with independent power, cooling, and networking.
- Availability zones are connected through high-speed, private fiber-optic networks.
- To ensure resiliency, a minimum of three separate availability zones are present in all availability zone-enabled regions.
- Availability zones are primarily for VMs, managed disks, load balancers, and SQL databases.

Azure services that support availability zones fall into three categories:
- **Zonal services**: You pin the resource to a specific zone (for example, VMs, managed disks, IP addresses).
- **Zone-redundant services**: The platform replicates automatically across zones (for example, zone-redundant storage, SQL Database).
- **Non-regional services**: Services are always available from Azure geographies and are resilient to zone-wide outages as well as region-wide outages.

### Region pairs
- Most Azure regions are paired with another region within the same geography (such as US, Europe, or Asia) at least 300 miles away.
- This approach allows for the replication of resources across a geography that helps reduce the likelihood of interruptions because of events such as natural disasters, civil unrest, power outages, or physical network outages that affect an entire region.
- If a region in a pair was affected by a natural disaster, services would automatically fail over to the other region in its region pair.
- Data continues to reside within the same geography as its pair (except for Brazil South) for tax- and law-enforcement jurisdiction purposes.
- Most regions are paired in two directions, meaning they are the backup for the region that provides a backup for them.
- However, some regions, such as West India and Brazil South, are paired in only one direction. In a one-direction pairing, the primary region does not provide backup for its secondary region.

### Sovereign Regions
- Sovereign regions are instances of Azure that are isolated from the main instance of Azure. You may need to use a sovereign region for compliance or legal purposes.

Azure sovereign regions include:
- **US DoD Central, US Gov Virginia, US Gov Iowa**, and more: These regions are physical and logical network-isolated instances of Azure for U.S. government agencies and partners. These datacenters are operated by screened U.S. personnel and include additional compliance certifications.
- **China East, China North**, and more: These regions are available through a unique partnership between Microsoft and 21Vianet, whereby Microsoft doesn't directly maintain the datacenters.

## Describe Azure management infrastructure

- The management infrastructure includes Azure resources and resource groups, subscriptions, and accounts.

### Azure resources and resource groups
- A resource is the basic building block of Azure. Anything you create, provision, deploy, etc. is a resource. Virtual Machines (VMs), virtual networks, databases, cognitive services, etc.
- Resource groups are simply groupings of resources. When you create a resource, you’re required to place it into a resource group.
- While a resource group can contain many resources, a single resource can only be in one resource group at a time.
- Additionally, resource groups can't be nested, meaning you can’t put resource group B inside of resource group A.
- If you delete a resource group, all the resources will be deleted.
- If you grant or deny access to a resource group, you’ve granted or denied access to all the resources within the resource group.

### Azure subscriptions
- In Azure, subscriptions are a unit of management, billing, and scale.
- A subscription provides you with authenticated and authorized access to Azure products and services. It also allows you to provision resources.
- An account can have multiple subscriptions, but it’s only required to have one.

There are two types of subscription boundaries that you can use:
- **Billing boundary**: This subscription type determines how an Azure account is billed for using Azure.
  - You can create multiple subscriptions for different types of billing requirements. Azure generates separate billing reports and invoices for each subscription so that you can organize and manage costs.
- **Access control boundary**: Azure applies access-management policies at the subscription level, and you can create separate subscriptions to reflect different organizational structures.
  - An example is that within a business, you have different departments to which you apply distinct Azure subscription policies.
  - This billing model allows you to manage and control access to the resources that users provision with specific subscriptions.

### Create additional Azure subscriptions

- **Environments**: You can choose to create subscriptions to set up separate environments for development and testing, security, or to isolate data for compliance reasons.
  - This design is particularly useful because resource access control occurs at the subscription level.
- **Organizational structures**: You can create subscriptions to reflect different organizational structures.
  - For example, you could limit one team to lower-cost resources, while allowing the IT department a full range.
  - This design allows you to manage and control access to the resources that users provision within each subscription.
- **Billing**: You can create additional subscriptions for billing purposes.
  - Because costs are first aggregated at the subscription level, you might want to create subscriptions to manage and track costs based on your needs.
  - For instance, you might want to create one subscription for your production workloads and another subscription for your development and testing workloads.

### Azure management groups
- Resources are gathered into resource groups, and resource groups are gathered into subscriptions.
- Azure management groups provide a level of scope above subscriptions.
- You organize subscriptions into containers called management groups and apply governance conditions to the management groups.
- All subscriptions within a management group automatically inherit the conditions applied to the management group, the same way that resource groups inherit settings from subscriptions and resources inherit from resource groups.
- Management groups give you enterprise-grade management at a large scale, no matter what type of subscriptions you might have.
- Management groups can be nested.

Examples of how you could use management groups:
- Create a hierarchy that applies a policy. You could limit VM locations to the US West Region in a group called Production. This security policy can't be altered by the resource or subscription owner, which allows for improved governance.
- Provide user access to multiple subscriptions. By moving multiple subscriptions under a management group, you can create one Azure role-based access control (Azure RBAC) assignment on the management group.

Important facts about management groups:
- 10,000 management groups can be supported in a single directory.
- A management group tree can support up to six levels of depth. This limit doesn't include the root level or the subscription level.
- Each management group and subscription can support only one parent.
