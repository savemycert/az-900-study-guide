# Domain 2: Describe Azure architecture and services (38%)

This is the heaviest domain. It covers how Azure is laid out physically and logically, then the core compute, networking, storage, and identity and security services. Nearly every question describes a need and asks you to pick the component or service that meets it.

## Describe the core architectural components of Azure

- **Physical layers:** datacenters form a region; regions sit inside a **geography** (for example, Europe), which helps with data residency.
- **Region:** one or more datacenters close together on a low-latency network; the location you pick at deploy time. Choose by proximity to users (latency), feature availability, price (varies by region), and compliance.
- **Region pair:** most regions are paired with a distant region in the same geography, so one large event is unlikely to hit both. Some services replicate to the pair, Microsoft restores one region of each pair first in a broad outage, and planned updates reach one region of a pair at a time. Example: East US with West US.
- **Sovereign regions:** isolated Azure instances kept separate from the global cloud for strict legal and regulatory needs. Examples: **Azure Government** (US government agencies and partners) and **Azure operated by 21Vianet** (China).
- **Availability zone:** a physically separate datacenter group inside one region with its own power, cooling, and networking. Zone-enabled regions have at least three.
  - **Zonal:** the resource is pinned to one zone and fails if that zone fails.
  - **Zone-redundant:** the service is spread across zones automatically and survives the loss of one.

- **Zones vs pairs:** zones give high availability inside one region; region pairs give disaster recovery across regions.
- **Logical hierarchy**, top to bottom:

| Level | Role | Remember |
|---|---|---|
| Management group | Groups subscriptions; can be nested to mirror the organization | Settings and access assigned here are inherited below |
| Subscription | Billing and access boundary; limits and quotas apply here | "Separate invoice" = separate subscription |
| Resource group | Logical container for a solution's resources | Delete the group = delete everything in it |
| Resource | One service instance (a VM, a storage account, a VNet) | Lives in exactly one resource group |

- Resources in one group can span regions and can be moved to another group.
- **Azure Resource Manager (ARM):** the deployment and management layer. Every create, update, or delete request, from the portal, command line, or templates, goes through ARM, which authenticates it and checks permissions.
- **Traps:**
  - A resource group is not a billing boundary. The subscription is.
  - Region pairs are about resilience. Sovereign regions are about isolation and compliance.

📖 Full lesson: [Azure Regions, Availability Zones & Resource Hierarchy](https://www.savemycert.com/revision/azure-fundamentals/azure-regions-availability-zones-architecture/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

## Describe Azure compute and networking services

- **Azure Virtual Machines (IaaS):** a full cloud computer. You manage the OS, patches, and installed software. Choose it for custom configurations, specific software, or lift and shift. Needs a disk, a VNet and network interface, and usually an IP address.
- **Containers:** an app packaged with its code, settings, and dependencies so it runs the same on any host. Lighter than VMs because containers share the host OS.
  - **Azure Container Instances (ACI):** run a single container quickly with no servers to manage.
  - **Azure Kubernetes Service (AKS):** orchestration for many containers: scheduling, restarting failed containers, scaling. Fits microservices.
- **Azure Functions (serverless):** event-driven code that runs when a trigger fires (file upload, message, timer). Scales automatically and is billed per execution, so idle code costs little or nothing. Poor fit for long-running or always-on work.
- **VM availability and scale options:**
  - **Virtual Machine Scale Sets:** a group of identical VMs whose count rises and falls with demand (autoscaling).
  - **Availability sets:** spread VMs across separate hardware so a hardware fault or maintenance does not take them all down at once.
  - **Azure Virtual Desktop:** Windows desktops and apps delivered from Azure to users anywhere.
- **Azure App Service (PaaS):** hosts web apps, REST APIs, and mobile back ends. The platform handles patching, load balancing, and scaling; you bring the code.
- **Networking:**
  - **Azure Virtual Network (VNet):** your private network in Azure, connecting resources to each other, to the internet when allowed, and to on-premises.
  - **Subnets:** ranges inside a VNet used to separate tiers (for example, web front end and database back end) and apply different rules.
  - **Peering:** links two VNets, including across regions, so they communicate privately over Microsoft's backbone.
  - **Azure DNS:** hosts your domain names in Azure and resolves them to addresses.

- **Azure VPN Gateway:** an encrypted site-to-site tunnel between your network and a VNet over the public internet. Cost-effective; performance varies with the internet.
- **Azure ExpressRoute:** a private, dedicated connection to Azure that does not use the public internet. More consistent performance, reliability, and security.
- **Traps:**
  - Scale Sets handle demand. Availability sets handle hardware failure. Neither is the other.
  - ACI is for a single container. Orchestrating many is AKS.

📖 Full lesson: [Azure Compute & Networking Services Explained](https://www.savemycert.com/revision/azure-fundamentals/azure-compute-networking-services/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

## Describe Azure storage services

| Service | Holds | Typical need |
|---|---|---|
| Azure Blob Storage | Unstructured objects | Images, video, logs, backups, files served to apps |
| Azure Files | Managed file shares (SMB or NFS) | Network drive for users or servers, replacing a file server |
| Azure Queue Storage | Messages | Passing work between parts of an application |
| Azure Table Storage | NoSQL key-value data | Simple structured, non-relational records |
| Azure Disk Storage | VM disks | OS and data disks for Azure VMs |

- **Blob Storage** is object storage (blob = binary large object). Blobs sit in **containers** inside a storage account, each with its own web address.
- **Access tiers (blobs only):** trade storage cost against access cost.
  - **Hot:** frequent access. Highest storage cost, lowest access cost.
  - **Cool:** infrequent access, kept at least about 30 days.
  - **Cold:** rarer still, longer minimum retention, cheaper storage.
  - **Archive:** rarely accessed, long-term. Cheapest to store but offline; reading data requires a retrieval that takes hours.
- **Redundancy (chosen per storage account):**
  - **LRS:** three copies in one datacenter. Cheapest; survives disk or server failure.
  - **ZRS:** copies across three availability zones in one region; survives a zone failure.
  - **GRS:** primary region plus replication to the paired secondary region; survives a regional outage.
  - **GZRS:** zone-redundant in the primary plus geo-replication; covers both.
- **Storage account:** the top-level container and namespace where you set region, redundancy, and performance.
  - **Standard general-purpose v2:** the usual default; supports blobs, files, queues, and tables and the access tiers.
  - **Premium:** SSD-backed for low latency (block blob, file share, and page blob variants).
- **Moving data:**
  - **AzCopy:** scriptable command-line bulk transfers for Blob and File storage.
  - **Azure Storage Explorer:** free desktop GUI to browse and transfer data.
  - **Azure File Sync:** mirrors an Azure Files share to an on-premises Windows file server that acts as a local cache.
- **Migrating:**
  - **Azure Migrate:** hub for assessing and migrating servers, databases, and apps.
  - **Azure Data Box:** a rugged physical device shipped to you for bulk offline transfer when the network is too slow.
- **Traps:**
  - LRS and ZRS never leave the region, so they do not survive a regional outage. Pick GRS or GZRS.
  - Archive data cannot be read immediately.
  - A shared drive over SMB is Files, not Blob.

📖 Full lesson: [Azure Storage Services, Tiers & Redundancy: AZ-900](https://www.savemycert.com/revision/azure-fundamentals/azure-storage-services/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

## Describe Azure identity, access, and security

- **Authentication** proves who you are. **Authorization** decides what you may do.
- **Microsoft Entra ID** (formerly Azure Active Directory, Azure AD): the cloud identity and directory service. Stores users and groups, verifies sign-ins to Azure, Microsoft 365, and other cloud apps, and is where SSO, MFA, and Conditional Access are enabled.
- **Microsoft Entra Domain Services:** managed traditional domain features (domain join, group policy, Kerberos and NTLM) without running your own domain controllers. For legacy apps that expect a Windows Server domain.
- **Authentication methods:**
  - **SSO:** sign in once, reach many apps. Fewer passwords to manage.
  - **Multifactor authentication (MFA):** two or more factors from different categories: something you know, have, or are. A stolen password alone is not enough.
  - **Passwordless:** no password at all; uses the Microsoft Authenticator app, Windows Hello, or a FIDO2 security key.
- **External identities:** partners and customers use their own accounts; you control their access.
- **Microsoft Entra Conditional Access:** if-then policies that evaluate sign-in signals (user location, device and its compliance, app, sign-in risk) and then allow, block, or require an extra step such as MFA. Example: always require MFA for administrators.
- **Azure RBAC:** assign roles for least-privilege access. An assignment = security principal (who) + role definition such as Reader, Contributor, or Owner (what) + scope such as subscription, resource group, or resource (where).
- **Zero Trust:** "never trust, always verify." Principles: verify explicitly, use least privilege, assume breach.
- **Defense in depth:** layered controls so one failure does not expose the data. Layers from outside in: physical, identity and access, perimeter, network, compute, application, data.
- **Microsoft Defender for Cloud:** security posture management (a **secure score** plus prioritized recommendations) and workload protection (threat detection and alerts for VMs, storage, databases, containers). Coverage can reach beyond Azure to other clouds and on-premises machines.
- **Traps:**
  - Reader can view but not change. Contributor can manage resources but cannot grant access to others.
  - Conditional Access decides whether a sign-in is allowed. RBAC decides what an allowed user can do.
  - Defender for Cloud covers security posture and threats; data cataloging is Purview (Domain 3).

📖 Full lesson: [Azure Identity, Access & Security: AZ-900 Guide](https://www.savemycert.com/revision/azure-fundamentals/azure-identity-access-security/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

[← Back to the study guide](../README.md)
