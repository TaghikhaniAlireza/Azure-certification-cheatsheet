
# Describe the core architectural components of Azure 
	## What does Azure offer?
		### Build intelligent apps and solutions with advanced technology, tools, and services to take your business to the next level. Seamlessly unify your technology to simplify platform management and to deliver innovations efficiently and securely on a trusted cloud.
	## Explore the Learn sandbox
		### Get-date
		### date
		### az version
			#### Azure command to check what version of the CLI you're using right now
		### az upgrade
			####  Try to run an update to the CLI
		### az interactive
			#### Enter az interactive to enter interactive mode.
	## Describe Azure physical infrastructure
		### Physical infrastructure
			#### The physical infrastructure for Azure starts with datacenters.
		### Regions
			#### A region is a geographical area on the planet that contains at least one, but potentially multiple datacenters that are nearby and networked together with a low-latency network.
		### Availability Zones
			#### Availability zones are physically separate datacenters within an Azure region. Each availability zone is made up of one or more datacenters equipped with independent power, cooling, and networking.
			#### Availability zones are connected through high-speed, private fiber-optic networks.
			#### 
			#### To ensure resiliency, a minimum of three separate availability zones are present in all availability zone-enabled regions.
			#### Availability zones are primarily for VMs, managed disks, load balancers, and SQL databases. Azure services that support availability zones fall into three categories:
				##### Zonal services: You pin the resource to a specific zone (for example, VMs, managed disks, IP addresses).
				##### Zone-redundant services: The platform replicates automatically across zones (for example, zone-redundant storage, SQL Database).
				##### Non-regional services: Services are always available from Azure geographies and are resilient to zone-wide outages as well as region-wide outages.
		### Region pairs
			#### Most Azure regions are paired with another region within the same geography (such as US, Europe, or Asia) at least 300 miles away
			#### This approach allows for the replication of resources across a geography that helps reduce the likelihood of interruptions because of events such as natural disasters, civil unrest, power outages, or physical network outages that affect an entire region.
			#### if a region in a pair was affected by a natural disaster, services would automatically fail over to the other region in its region pair.
			#### 
			#### Data continues to reside within the same geography as its pair (except for Brazil South) for tax- and law-enforcement jurisdiction purposes.
			#### Most regions are paired in two directions, meaning they are the backup for the region that provides a backup for them
			#### However, some regions, such as West India and Brazil South, are paired in only one direction. In a one-direction pairing, the Primary region does not provide backup for its secondary region.
		### Sovereign Regions
			#### Sovereign regions are instances of Azure that are isolated from the main instance of Azure. You may need to use a sovereign region for compliance or legal purposes.
			#### Azure sovereign regions include:
				##### US DoD Central, US Gov Virginia, US Gov Iowa and more: These regions are physical and logical network-isolated instances of Azure for U.S. government agencies and partners. These datacenters are operated by screened U.S. personnel and include additional compliance certifications.
				##### China East, China North, and more: These regions are available through a unique partnership between Microsoft and 21Vianet, whereby Microsoft doesn't directly maintain the datacenters.
	## Describe Azure management infrastructure
		### The management infrastructure includes Azure resources and resource groups, subscriptions, and accounts. 
		### Azure resources and resource groups
			#### A resource is the basic building block of Azure. Anything you create, provision, deploy, etc. is a resource. Virtual Machines (VMs), virtual networks, databases, cognitive services, etc.
			#### Resource groups are simply groupings of resources. When you create a resource, you’re required to place it into a resource group.
			#### While a resource group can contain many resources, a single resource can only be in one resource group at a time.
			#### Additionally, resource groups can't be nested, meaning you can’t put resource group B inside of resource group A.
			#### If you delete a resource group, all the resources will be deleted.
			#### If you grant or deny access to a resource group, you’ve granted or denied access to all the resources within the resource group.
		### Azure subscriptions
			#### In Azure, subscriptions are a unit of management, billing, and scale.
			#### A subscription provides you with authenticated and authorized access to Azure products and services. It also allows you to provision resources.
			#### An account can have multiple subscriptions, but it’s only required to have one. 
			#### There are two types of subscription boundaries that you can use:
				##### Billing boundary: This subscription type determines how an Azure account is billed for using Azure. 
					###### You can create multiple subscriptions for different types of billing requirements. Azure generates separate billing reports and invoices for each subscription so that you can organize and manage costs.
				##### Access control boundary: Azure applies access-management policies at the subscription level, and you can create separate subscriptions to reflect different organizational structures. 
					###### An example is that within a business, you have different departments to which you apply distinct Azure subscription policies. 
					###### This billing model allows you to manage and control access to the resources that users provision with specific subscriptions.
		### Create additional Azure subscriptions
			#### Environments: You can choose to create subscriptions to set up separate environments for development and testing, security, or to isolate data for compliance reasons. 
				##### This design is particularly useful because resource access control occurs at the subscription level.
			#### Organizational structures: You can create subscriptions to reflect different organizational structures. 
				##### For example, you could limit one team to lower-cost resources, while allowing the IT department a full range. 
				##### This design allows you to manage and control access to the resources that users provision within each subscription.
			#### Billing: You can create additional subscriptions for billing purposes. 
				##### Because costs are first aggregated at the subscription level, you might want to create subscriptions to manage and track costs based on your needs. 
				##### For instance, you might want to create one subscription for your production workloads and another subscription for your development and testing workloads.
		### Azure management groups
			#### Resources are gathered into resource groups, and resource groups are gathered into subscriptions.
			#### Azure management groups provide a level of scope above subscriptions. 
			#### You organize subscriptions into containers called management groups and apply governance conditions to the management groups. 
			#### All subscriptions within a management group automatically inherit the conditions applied to the management group, the same way that resource groups inherit settings from subscriptions and resources inherit from resource groups. 
			#### Management groups give you enterprise-grade management at a large scale, no matter what type of subscriptions you might have. Management groups can be nested.
		### 
			#### Some examples of how you could use management groups might be:
				##### Create a hierarchy that applies a policy. You could limit VM locations to the US West Region in a group called Production. This security policy can't be altered by the resource or subscription owner, which allows for improved governance.
				##### Provide user access to multiple subscriptions. By moving multiple subscriptions under a management group, you can create one Azure role-based access control (Azure RBAC) assignment on the management group.
			#### Important facts about management groups:
				##### 10,000 management groups can be supported in a single directory.
				##### A management group tree can support up to six levels of depth. This limit doesn't include the root level or the subscription level.
				##### Each management group and subscription can support only one parent.
		
# Describe Azure compute and networking services 
	## Describe Azure virtual machines
		### With Azure Virtual Machines (VMs), you can create and use VMs in the cloud. VMs are an ideal choice when you need:
			####     Total control over the operating system (OS).
			####     The ability to run custom software.
			####     To use custom hosting configurations.
		### An image is a template used to create a VM and may already include an OS and other software, like development tools or web hosting environments.
		### Virtual machine scale sets
			#### Virtual machine scale sets let you create and manage a group of identical, load-balanced VMs.
			#### Scale sets allow you to centrally manage, configure, and update a large number of VMs in minutes.
			#### Virtual machine scale sets also automatically deploy a load balancer to make sure that your resources are being used efficiently. 
			#### With virtual machine scale sets, you can build large-scale services for areas such as compute, big data, and container workloads.
		### Virtual machine availability sets
			#### Availability accomplish these objectives by grouping VMs in two ways: 
				##### update domain 
					###### The update domain groups VMs that can be rebooted at the same time.
				##### fault domain.
					###### The fault domain groups your VMs by common power source and network switch. By default, an availability set splits your VMs across up to three fault domains.
					###### This helps protect against a physical power or networking failure by having VMs in different fault domains
		### Create a Linux virtual machine and install Nginx
			#### az vm create \
			####   --resource-group "[sandbox resource group name]" \
			####   --name my-vm \
			####   --public-ip-sku Standard \
			####   --image Ubuntu2204 \
			####   --admin-username azureuser \
			####   --generate-ssh-keys    
		### Run the following az vm extension set command to configure Nginx on your VM:
			#### az vm extension set \
			####   --resource-group "[sandbox resource group name]" \
			####   --vm-name my-vm \
			####   --name customScript \
			####   --publisher Microsoft.Azure.Extensions \
			####   --version 2.1 \
			####   --settings '{"fileUris":["https://raw.githubusercontent.com/MicrosoftDocs/mslearn-welcome-to-azure/master/configure-nginx.sh"]}' \
			####   --protected-settings '{"commandToExecute": "./configure-nginx.sh"}'    
	## Describe Azure virtual desktop
		### It enables you to use a cloud-hosted version of Windows from any location. Azure Virtual Desktop works across devices and operating systems, and works with apps that you can use to access remote desktops or most modern browsers.
		### Azure Virtual Desktop provides centralized security management for users' desktops with Microsoft Entra ID
		### With Azure Virtual Desktop, the data and apps are separated from the local hardware.
		### Azure Virtual Desktop lets you use Windows 10 or Windows 11 Enterprise multi-session, the only Windows client-based operating system that enables multiple concurrent users on a single VM.
		###  You can also secure access to data by assigning granular role-based access controls (RBACs) to users.
	## Describe Azure containers
		### If you want to run multiple instances of an application on a single host machine, containers are an excellent choice.
		### Containers are often used to create solutions by using a microservice architecture. 
		### Containers are a virtualization environment. 
		### Much like running multiple virtual machines on a single physical host, you can run multiple containers on a single physical or virtual host.
		### Unlike virtual machines, you don't manage the operating system for a container.
			#### Azure Container Instances
				##### Azure Container Instances offer the fastest and simplest way to run a container in Azure
				##### Azure Container Instances are a platform as a service (PaaS) offering. 
				##### Azure Container Instances allow you to upload your containers and then the service runs the containers for you.
			#### Azure Container Apps
				##### They allow you to get up and running right away, they remove the container management piece, and they're a PaaS offering. 
				##### Container Apps have extra benefits such as the ability to incorporate load balancing and scaling. 
			#### Azure Kubernetes Service
				##### Azure Kubernetes Service (AKS) is a container orchestration service.
	## Describe Azure functions
		### Azure Functions is an event-driven, serverless compute option that doesn’t require maintaining virtual machines or containers.
		### Using Azure Functions is ideal when you're only concerned about the code running your service and not about the underlying platform or infrastructure.
		### Functions are commonly used when you need to perform work in response to an event (often via a REST request), timer, or message from another Azure service, and when that work can be completed quickly, within seconds or less.
		### In this model, Azure only charges you for the CPU time used while your function runs.
		### Functions can be either stateless or stateful. When they're stateless (the default), they behave as if they restart every time they respond to an event. 
		### When they're stateful (called Durable Functions), a context is passed through the function to track prior activity.
	## Describe application hosting options
		### Azure App Service
			#### App Service enables you to build and host web apps, background jobs, mobile back-ends, and RESTful APIs
			####  offers automatic scaling and high availability. 
			#### App Service supports Windows and Linux. 
			#### It enables automated deployments from GitHub, Azure DevOps, or any Git repo to support a continuous deployment model.
			#### Azure App Service is an HTTP-based service for hosting web applications, REST APIs, and mobile back ends. It supports multiple languages, including .NET, .NET Core, Java, Ruby, Node.js, PHP, or Python. It also supports both Windows and Linux environments
		### Types of app services
			####     Web apps
				##### App Service includes full support for hosting web apps by using ASP.NET, ASP.NET Core, Java, Ruby, Node.js, PHP, or Python. You can choose either Windows or Linux as the host operating system.
			####     API apps
				##### you can build REST-based web APIs by using your choice of language and framework.
			####     WebJobs
				##### You can use the WebJobs feature to run a program (.exe, Java, PHP, Python, or Node.js) or script (.cmd, .bat, PowerShell, or Bash) in the same context as a web app, API app, or mobile app. They can be scheduled or run by a trigger. 
				##### WebJobs are often used to run background tasks as part of your application logic.
			####     Mobile apps
				#####     Store mobile app data in a cloud-based SQL database.
				#####     Authenticate customers against common social providers, such as MSA, Google, X, and Facebook.
				#####     Send push notifications.
				#####     Execute custom back-end logic in C# or Node.js.
			#### On the mobile app side, there's SDK support for native iOS and Android, Xamarin, and React native apps.
	## Describe Azure virtual networking
		### Azure virtual networking supports both public and private endpoints to enable communication between external or internal resources with other internal resources.
			####     Public endpoints have a public IP address and can be accessed from anywhere in the world.
			####     Private endpoints exist within a virtual network and have a private IP address from within the address space of that virtual network.
		### Azure virtual networks provide the following key networking capabilities:
			####     Isolation and segmentation
				##### Azure virtual network allows you to create multiple isolated virtual networks. 
				##### For name resolution, you can use the name resolution service built into Azure. You also can configure the virtual network to use either an internal or an external DNS server.
			####     Internet communications
				##### You can enable incoming connections from the internet by assigning a public IP address to an Azure resource, or putting the resource behind a public load balancer.
			####     Communicate between Azure resources
				##### Virtual networks can connect not only VMs but other Azure resources, such as the App Service Environment for Power Apps, Azure Kubernetes Service, and Azure virtual machine scale sets.
				##### Service endpoints can connect to other Azure resource types, such as Azure SQL databases and storage accounts. 
			####     Communicate with on-premises resources
				##### you can create a network that spans both your local and cloud environments.
				##### There are three mechanisms for you to achieve this connectivity:
					######     Point-to-site virtual private network connections are from a computer outside your organization back into your corporate network. In this case, the client computer initiates an encrypted VPN connection to connect to the Azure virtual network.
					######     Site-to-site virtual private networks link your on-premises VPN device or gateway to the Azure VPN gateway in a virtual network. In effect, the devices in Azure can appear as being on the local network. The connection is encrypted and works over the internet.
					######     Azure ExpressRoute provides a dedicated private connectivity to Azure that doesn't travel over the internet. ExpressRoute is useful for environments where you need greater bandwidth and even higher levels of security.
			####     Route network traffic
				##### By default, Azure routes traffic between subnets on any connected virtual networks, on-premises networks, and the internet. You also can control routing and override those settings, as follows:
					######     Route tables allow you to define rules about how traffic should be directed. You can create custom route tables that control how packets are routed between subnets.
					######     Border Gateway Protocol (BGP) works with Azure VPN gateways, Azure Route Server, or Azure ExpressRoute to propagate on-premises BGP routes to Azure virtual networks.
			####     Filter network traffic
				##### Azure virtual networks enable you to filter traffic between subnets by using the following approaches:
					######     Network security groups are Azure resources that can contain multiple inbound and outbound security rules. You can define these rules to allow or block traffic, based on factors such as source and destination IP address, port, and protocol.
					######     Network virtual appliances are specialized VMs that can be compared to a hardened network appliance. A network virtual appliance carries out a particular network function, such as running a firewall or performing wide area network (WAN) optimization.
			####     Connect virtual networks
				##### You can link virtual networks together by using virtual network peering. 
				##### Peering allows two virtual networks to connect directly to each other. 
				##### Network traffic between peered networks is private, and travels on the Microsoft backbone network, never entering the public internet.
				##### Peering enables resources in each virtual network to communicate with each other. 
				##### These virtual networks can be in separate regions. This feature allows you to create a global interconnected network through Azure.
			#### User-defined routes (UDR) allow you to control the routing tables between subnets within a virtual network or between virtual networks. 
	## Exercise - Configure network access
		### To verify the VM you created previously is still running, use the following command:
			#### az vm list
		### Run the following  command to get your VM's IP address and store the result as a Bash variable
			#### az vm list-ip-addresses
		### List the current network security group rules
			#### az network nsg list \
			####   --resource-group "[sandbox resource group name]" \
			####   --query '[].name' \
			####   --output tsv    
			#### Every VM on Azure is associated with at least one network security group.
		### Run the following  command to list the rules associated with the NSG named my-vmNSG:
			#### az network nsg rule list \
			####   --resource-group "[sandbox resource group name]" \
			####   --nsg-name my-vmNSG    
		### Create the network security rule
			#### az network nsg rule create \
			####   --resource-group "[sandbox resource group name]" \
			####   --nsg-name my-vmNSG \
			####   --name allow-http \
			####   --protocol tcp \
			####   --priority 100 \
			####   --destination-port-range 80 \
			####   --access Allow    
	## Describe Azure virtual private networks
		### A virtual private network (VPN) uses an encrypted tunnel within another network. 
		### VPN gateways
			#### Azure VPN Gateway instances are deployed in a dedicated subnet of the virtual network and enable the following connectivity:
				#####     Connect on-premises datacenters to virtual networks through a site-to-site connection.
				#####     Connect individual devices to virtual networks through a point-to-site connection.
				#####     Connect virtual networks to other virtual networks through a network-to-network connection.
			#### You can deploy only one VPN gateway in each virtual network. However, you can use one gateway to connect to multiple locations, which includes other virtual networks or on-premises datacenters.
		### When setting up a VPN gateway, you must specify the type of VPN - either policy-based or route-based.
			#### Policy-based VPN gateways specify statically the IP address of packets that should be encrypted through each tunnel. 
				##### This type of device evaluates every data packet against those sets of IP addresses to choose the tunnel where that packet is going to be sent through.
			#### In Route-based gateways, IPSec tunnels are modeled as a network interface or virtual tunnel interface. 
				##### IP routing (either static routes or dynamic routing protocols) decides which one of these tunnel interfaces to use when sending each packet. 
				##### Route-based VPNs are the preferred connection method for on-premises devices. 
				##### They're more resilient to topology changes such as the creation of new subnets.
			#### Use a route-based VPN gateway if you need any of the following types of connectivity:
				#####     Connections between virtual networks
				#####     Point-to-site connections
				#####     Multisite connections
				#####     Coexistence with an Azure ExpressRoute gateway
		### High-availability scenarios
			#### Active/standby
				##### By default, VPN gateways are deployed as two instances in an active/standby configuration, even if you only see one VPN gateway resource in Azure.
				##### they typically restore within a few seconds for planned maintenance and within 90 seconds for unplanned disruptions.
			#### Active/active
				##### With the introduction of support for the BGP routing protocol, you can also deploy VPN gateways in an active/active configuration.
				##### In this configuration, you assign a unique public IP address to each instance. 
				##### You then create separate tunnels from the on-premises device to each IP address. 
				##### You can extend the high availability by deploying an additional VPN device on-premises.
			#### ExpressRoute failover
				##### In high-availability scenarios, where there's risk associated with an outage of an ExpressRoute circuit, you can also provision a VPN gateway that uses the internet as an alternative method of connectivity.
			#### Zone-redundant gateways
				##### In regions that support availability zones, VPN gateways and ExpressRoute gateways can be deployed in a zone-redundant configuration. 
				##### This configuration brings resiliency, scalability, and higher availability to virtual network gateways. 
				##### Deploying gateways in Azure availability zones physically and logically separates gateways within a region while protecting your on-premises network connectivity to Azure from zone-level failures. 
				##### These gateways require different gateway stock keeping units (SKUs) and use Standard public IP addresses instead of Basic public IP addresses.
	## Describe Azure ExpressRoute
		### You can enable ExpressRoute Global Reach to exchange data across your on-premises sites by connecting your ExpressRoute circuits. 
		### This feature allows you to connect offices, datacenters, or other facilities to the Microsoft cloud. Each location would have its own ExpressRoute circuit.
		### Connectivity can be from an any-to-any (IP VPN) network, a point-to-point Ethernet network, or a virtual cross-connection through a connectivity provider at a colocation facility.
			#### There are several benefits to using ExpressRoute as the connection service between Azure and on-premises networks.
			####     Connectivity to Microsoft cloud services across all regions in the geopolitical region.
			####     Global connectivity to Microsoft services across all regions with the ExpressRoute Global Reach.
			####     Dynamic routing between your network and Microsoft via Border Gateway Protocol (BGP).
			####     Built-in redundancy in every peering location for higher reliability.
		### ExpressRoute enables direct access to the following services in all regions:
			####     Microsoft Office 365
			####     Microsoft Dynamics 365
			####     Azure compute services, such as Azure Virtual Machines
			####     Azure cloud services, such as Azure Cosmos DB and Azure Storage
		### ExpressRoute uses the BGP. BGP is used to exchange routes between on-premises networks and resources running in Azure. This protocol enables dynamic routing between your on-premises network and services running in the Microsoft cloud.
		### ExpressRoute supports four models that you can use to connect your on-premises network to the Microsoft cloud:
			#### CloudExchange colocation
				##### Colocation refers to your datacenter, office, or other facility being physically colocated at a cloud exchange, such as an ISP. 
				##### If your facility is colocated at a cloud exchange, you can request a virtual cross-connect to the Microsoft cloud.
			#### Point-to-point Ethernet connection
				##### Point-to-point ethernet connection refers to using a point-to-point connection to connect your facility to the Microsoft cloud.
			#### Any-to-any connection
				##### Azure integrates with your WAN connection to provide a connection like you would have between your datacenter and any branch offices.
			#### Directly from ExpressRoute sites
				##### You can connect directly into the Microsoft's global network at a peering location strategically distributed across the world. 
				##### ExpressRoute Direct provides dual 100 Gbps or 10-Gbps connectivity, which supports Active/Active connectivity at scale.
		### Security considerations
			#### With ExpressRoute, your data doesn't travel over the public internet, reducing the risks associated with internet communications. 
			#### ExpressRoute is a private connection from your on-premises infrastructure to your Azure infrastructure. 
			#### Even if you have an ExpressRoute connection, DNS queries, certificate revocation list checking, and Azure Content Delivery Network requests are still sent over the public internet.
	## Describe Azure DNS
		### Azure DNS is a hosting service for DNS domains that provides name resolution by using Microsoft Azure infrastructure. 
		### By hosting your domains in Azure, you can manage your DNS records using the same credentials, APIs, tools, and billing as your other Azure services.
		### Azure DNS uses the scope and scale of Microsoft Azure to provide numerous benefits, including:
			#### Reliability and performance
				##### DNS domains in Azure DNS are hosted on Azure's global network of DNS name servers, providing resiliency and high availability. 
				##### Azure DNS uses anycast networking, so the closest available DNS server answers each DNS query, providing fast performance and high availability for your domain.
			#### Security
				##### Azure DNS is based on Azure Resource Manager, which provides features such as:
					###### Azure role-based access control (Azure RBAC) to control who has access to specific actions for your organization.
					###### Activity logs to monitor how a user in your organization modified a resource or to find an error when troubleshooting.
					###### Resource locking to lock a subscription, resource group, or resource. Locking prevents other users in your organization from accidentally deleting or modifying critical resources.
			#### Ease of Use
				##### Azure DNS is integrated in the Azure portal and uses the same credentials, support contract, and billing as your other Azure services.
				##### Because Azure DNS is running on Azure, it means you can manage your domains and records with the Azure portal, Azure PowerShell cmdlets, and the cross-platform Azure CLI. 
				##### Applications that require automated DNS management can integrate with the service by using the REST API and SDKs.
			#### Customizable virtual networks
				##### Azure DNS also supports private DNS domains. 
				##### This feature allows you to use your own custom domain names in your private virtual networks, rather than being stuck with the Azure-provided names.
			#### Alias records
				##### You can use an alias record set to refer to an Azure resource, such as an Azure public IP address, an Azure Traffic Manager profile, or an Azure Content Delivery Network (CDN) endpoint. 
				##### If the IP address of the underlying resource changes, the alias record set seamlessly updates itself during DNS resolution. 
				##### The alias record set points to the service instance, and the service instance is associated with an IP address.
		### Important
			#### You can't use Azure DNS to buy a domain name. For an annual fee, you can buy a domain name by using App Service domains or a third-party domain name registrar. Once purchased, your domains can be hosted in Azure DNS for record management.
		
# Describe Azure storage services 
	## Describe Azure storage accounts
		### A storage account provides a unique namespace for your Azure Storage data that's accessible from anywhere in the world over HTTP or HTTPS. 
		### The type of account determines the storage services and redundancy options and has an impact on the use cases. 
		### Below is a list of redundancy options that will be covered later in this module:
			#### Locally redundant storage (LRS)
			#### Geo-redundant storage (GRS)
			#### Read-access geo-redundant storage (RA-GRS)
			#### Zone-redundant storage (ZRS)
			#### Geo-zone-redundant storage (GZRS)
			#### Read-access geo-zone-redundant storage (RA-GZRS)
		### 
		### every storage account in Azure must have a unique-in-Azure account name.
		### When naming your storage account, keep these rules in mind:
			#### Storage account names must be between 3 and 24 characters in length and may contain numbers and lowercase letters only.
			#### Your storage account name must be unique within Azure. No two storage accounts can have the same name. This supports the ability to have a unique, accessible namespace in Azure.
		### 

	## Describe Azure storage redundancy
		### Azure Storage always stores multiple copies of your data so that it's protected from planned and unplanned events such as transient hardware failures, network or power outages, and natural disasters. 
		### The factors that help determine which redundancy option you should choose include:
			#### How your data is replicated in the primary region.
			#### Whether your data is replicated to a second region that is geographically distant to the primary region, to protect against regional disasters.
			#### Whether your application requires read access to the replicated data in the secondary region if the primary region becomes unavailable.
		### Redundancy in the primary region
			#### Data in an Azure Storage account is always replicated three times in the primary region. Azure Storage offers two options :
				##### Locally redundant storage
					###### Locally redundant storage (LRS) replicates your data three times within a single data center in the primary region. 
					###### LRS provides at least 11 nines of durability (99.999999999%) of objects over a given year.
					###### 
					###### LRS is the lowest-cost redundancy option and offers the least durability compared to other options. 
					###### if a disaster such as fire or flooding occurs within the data center, all replicas of a storage account using LRS may be lost or unrecoverable.
				##### Zone-redundant storage
					###### For Availability Zone-enabled Regions, zone-redundant storage (ZRS) replicates your Azure Storage data synchronously across three Azure availability zones in the primary region. 
					###### ZRS offers durability for Azure Storage data objects of at least 12 nines (99.9999999999%) over a given year.
					###### 
					###### With ZRS, your data is still accessible for both read and write operations even if a zone becomes unavailable. 
					###### Microsoft recommends using ZRS in the primary region for scenarios that require high availability. 
					###### ZRS is also recommended for restricting replication of data within a country or region to meet data governance requirements.
		### Redundancy in a secondary region
			#### For applications requiring high durability, you can choose to additionally copy the data in your storage account to a secondary region that is hundreds of miles away from the primary region
			#### The paired secondary region is based on Azure Region Pairs, and can't be changed.
			#### Azure Storage offers two options for copying your data to a secondary region:
				##### GRS is similar to running LRS in two regions, and GZRS is similar to running ZRS in the primary region and LRS in the secondary region.
				##### By default, data in the secondary region isn't available for read or write access unless there's a failover to the secondary region.
				##### Important
					###### Because data is replicated to the secondary region asynchronously, a failure that affects the primary region may result in data loss if the primary region can't be recovered. 
					###### The interval between the most recent writes to the primary region and the last write to the secondary region is known as the recovery point objective (RPO). 
					###### The RPO indicates the point in time to which data can be recovered. 
					###### Azure Storage typically has an RPO of less than 15 minutes, although there's currently no SLA on how long it takes to replicate data to the secondary region.
				##### Geo-redundant storage(GRS)
					###### GRS copies your data synchronously three times within a single physical location in the primary region using LRS. 
					###### It then copies your data asynchronously to a single physical location in the secondary region (the region pair) using LRS. 
					###### GRS offers durability for Azure Storage data objects of at least 16 nines (99.99999999999999%) over a given year.
					###### 
					
				##### Geo-zone-redundant storage(GZRS)
					###### Data in a GZRS storage account is copied across three Azure availability zones in the primary region (similar to ZRS) and is also replicated to a secondary geographic region, using LRS, for protection from regional disasters. 
					###### Microsoft recommends using GZRS for applications requiring maximum consistency, durability, and availability, excellent performance, and resilience for disaster recovery.
					###### 
		### Read access to data in the secondary region
			#### Geo-redundant storage (with GRS or GZRS) replicates your data to another physical location in the secondary region to protect against regional outages. 
			#### However, that data is available to be read only if the customer or Microsoft initiates a failover from the primary to secondary region. 
			#### However, if you enable read access to the secondary region, your data is always available, even when the primary region is running optimally. 
			#### For read access to the secondary region, enable read-access geo-redundant storage (RA-GRS) or read-access geo-zone-redundant storage (RA-GZRS).
			#### Remember that the data in your secondary region may not be up-to-date due to RPO.
	## Describe Azure storage services
		### Azure Blobs: A massively scalable object store for text and binary data. Also includes support for big data analytics through Data Lake Storage Gen2.
			#### Azure Blob storage is an object storage solution for the cloud. It can store massive amounts of data, such as text or binary data. 
			#### Azure Blob storage is unstructured, meaning that there are no restrictions on the kinds of data it can hold. 
			#### Blob storage can manage thousands of simultaneous uploads, massive amounts of video data, constantly growing log files, and can be reached from anywhere with an internet connection.
			#### Blobs aren't limited to common file formats. A blob could contain gigabytes of binary data streamed from a scientific instrument, an encrypted message for another application, or data in a custom format for an app you're developing.
			#### Blob storage is ideal for:
				##### Serving images or documents directly to a browser.
				##### Storing files for distributed access.
				##### Streaming video and audio.
				##### Storing data for backup and restore, disaster recovery, and archiving.
				##### Storing data for analysis by an on-premises or Azure-hosted service.
			#### Accessing blob storage
				##### Objects in blob storage can be accessed from anywhere in the world via HTTP or HTTPS. 
				##### Users or client applications can access blobs via URLs, the Azure Storage REST API, Azure PowerShell, Azure CLI, or an Azure Storage client library. 
				##### The storage client libraries are available for multiple languages, including .NET, Java, Node.js, Python, PHP, and Ruby.
			#### Blob storage tiers
				##### Hot access tier: Optimized for storing data that is accessed frequently (for example, images for your website).
				##### Cool access tier: Optimized for data that is infrequently accessed and stored for at least 30 days (for example, invoices for your customers).
				##### Cold access tier: Optimized for storing data that is infrequently accessed and stored for at least 90 days.
				##### Archive access tier: Appropriate for data that is rarely accessed and stored for at least 180 days, with flexible latency requirements (for example, long-term backups).
			#### The following considerations apply to the different access tiers:
				##### Hot, cool, and cold access tiers can be set at the account level. The archive access tier isn't available at the account level.
				##### Hot, cool, cold, and archive tiers can be set at the blob level, during or after upload.
				##### Data in the cool and cold access tiers can tolerate slightly lower availability, but still requires high durability, retrieval latency, and throughput characteristics similar to hot data. For cool and cold data, a lower availability service-level agreement (SLA) and higher access costs compared to hot data are acceptable trade-offs for lower storage costs.
				##### Archive storage stores data offline and offers the lowest storage costs, but also the highest costs to rehydrate and access data.
		### Azure Files: Managed file shares for cloud or on-premises deployments.
			#### Azure File storage offers fully managed file shares in the cloud that are accessible via the industry standard Server Message Block (SMB) or Network File System (NFS) protocols.
			#### SMB Azure file shares are accessible from Windows, Linux, and macOS clients. 
			#### NFS Azure Files shares are accessible from Linux or macOS clients. 
			#### SMB Azure file shares can be cached on Windows Servers with Azure File Sync for fast access near where the data is being used.
			#### PowerShell cmdlets and Azure CLI can be used to create, mount, and manage Azure file shares as part of the administration of Azure applications. You can create and manage Azure file shares using Azure portal and Azure Storage Explorer.
			#### Resiliency: Azure Files has been built from the ground up to always be available. Replacing on-premises file shares with Azure Files means you don't have to wake up in the middle of the night to deal with local power outages or network issues.
		### Azure Queues: A messaging store for reliable messaging between application components.
			#### Azure Queue storage is a service for storing large numbers of messages. 
			#### Once stored, you can access the messages from anywhere in the world via authenticated calls using HTTP or HTTPS. 
			#### Each individual message can be up to 64 KB in size.
			#### Queue storage can be combined with compute functions like Azure Functions to take an action when a message is received.
		### Azure Disks: Block-level storage volumes for Azure VMs.
			#### Azure Disk storage, or Azure managed disks, are block-level storage volumes managed by Azure for use with Azure VMs. 
			#### Conceptually, they’re the same as a physical disk, but they’re virtualized – offering greater resiliency and availability than a physical disk. 
		### Azure Tables: NoSQL table option for structured, non-relational data.
			#### Azure Table storage stores large amounts of structured data. 
			#### Azure tables are a NoSQL datastore that accepts authenticated calls from inside and outside the Azure cloud. 
			#### This enables you to use Azure tables to build your hybrid or multicloud solution and have your data always available. 
			#### Azure tables are ideal for storing structured, non-relational data.
	## Identify Azure data migration options
		### Azure Migrate
			#### Azure Migrate is a service that helps you migrate from an on-premises environment to the cloud. 
			#### Unified migration platform: A single portal to start, run, and track your migration to Azure.
			#### Range of tools: A range of tools for assessment and migration. Azure Migrate tools include Azure Migrate: Discovery and assessment and Azure Migrate: Server Migration. Azure Migrate also integrates with other Azure services and tools, and with independent software vendor (ISV) offerings.
			####  Assessment and migration: In the Azure Migrate hub, you can assess and migrate your on-premises infrastructure to Azure.
		### Integrated tools
			#### Azure Migrate: Discovery and assessment. Discover and assess on-premises servers running on VMware, Hyper-V, and physical servers in preparation for migration to Azure.
			#### Azure Migrate: Server Migration. Migrate VMware VMs, Hyper-V VMs, physical servers, other virtualized servers, and public cloud VMs to Azure.
			#### Data Migration Assistant. Data Migration Assistant is a stand-alone tool to assess SQL Servers. It helps pinpoint potential problems blocking migration. It identifies unsupported features, new features that can benefit you after migration, and the right path for database migration.
			#### Azure Database Migration Service. Migrate on-premises databases to Azure VMs running SQL Server, Azure SQL Database, or SQL Managed Instances.
			#### Azure App Service migration assistant. Azure App Service migration assistant is a standalone tool to assess on-premises websites for migration to Azure App Service. Use Migration Assistant to migrate .NET and PHP web apps to Azure.
			#### Azure Data Box. Use Azure Data Box products to move large amounts of offline data to Azure.
		### Azure Data Box
			#### Azure Data Box is a physical migration service that helps transfer large amounts of data in a quick, inexpensive, and reliable way. 
			#### The secure data transfer is accelerated by shipping you a proprietary Data Box storage device that has a maximum usable storage capacity of 80 terabytes. 
		### Use cases
			#### Data Box is ideally suited to transfer data sizes larger than 40 TBs in scenarios with no to limited network connectivity. 
			#### Onetime migration - when a large amount of on-premises data is moved to Azure.
			#### Migrating your VM farm, SQL server, and applications to Azure.
			#### Periodic uploads - when large amount of data is generated periodically and needs to be moved to Azure.
			#### Migrate back to on-premises or to another cloud service provider
		### Once the data from your import order is uploaded to Azure, the disks on the device are wiped clean in accordance with NIST 800-88r1 standards. 
	## Identify Azure file movement options
		### help you move or interact with individual files or small file groups.
		### AzCopy
			#### AzCopy is a command-line utility that you can use to copy blobs or files to or from your storage account.
			#### AzCopy can even be configured to work with other cloud providers to help move files back and forth between clouds.
			#### Synchronizing blobs or files with AzCopy is one-direction synchronization.
			####  It doesn't synchronize bi-directionally based on timestamps or other metadata.
		### Azure Storage Explorer
			#### Azure Storage Explorer is a standalone app that provides a graphical interface to manage files and blobs in your Azure Storage Account.
		### Azure File Sync
			#### Azure File Sync is a tool that lets you centralize your file shares in Azure Files and keep the flexibility, performance, and compatibility of a Windows file server. 
			#### Once you install Azure File Sync on your local Windows server, it will automatically stay bi-directionally synced with your files in Azure.
			#### With Azure File Sync, you can:
				##### Use any protocol that's available on Windows Server to access your data locally, including SMB, NFS, and FTPS.
				##### Have as many caches as you need across the world.
				##### Replace a failed local server by installing Azure File Sync on a new server in the same datacenter.
				##### Configure cloud tiering so the most frequently accessed files are replicated locally, while infrequently accessed files are kept in the cloud until requested.
				
# Describe Azure identity, access, and security 













