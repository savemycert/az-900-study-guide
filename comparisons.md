# AZ-900 Commonly Confused Services and Concepts

Side-by-side comparisons of the AZ-900 services and ideas that exam questions most often set against each other. Each table ends with the one thing to remember.

- [Domain 1: Describe cloud concepts](#domain-1-describe-cloud-concepts)
- [Domain 2: Describe Azure architecture and services](#domain-2-describe-azure-architecture-and-services)
- [Domain 3: Describe Azure management and governance](#domain-3-describe-azure-management-and-governance)

## Domain 1: Describe cloud concepts

### IaaS vs PaaS vs SaaS

| | IaaS | PaaS | SaaS |
|---|---|---|---|
| What it is | Rented infrastructure: VMs, storage, networking | A managed platform to build and run your own apps | Finished software delivered over the internet |
| Who manages the OS | You | Provider | Provider |
| You still manage | OS, runtime, apps, data | Application code and data | Data, user access, app settings |
| Use it when | Lift and shift, full OS control, dev/test | Building an app or API without managing servers | Email, collaboration, CRM that staff just sign in to |
| Azure examples | Azure Virtual Machines | Azure App Service, Azure SQL Database | Microsoft 365, Dynamics 365 |
| Exam cue | "you manage the operating system" | "deploy your code, provider patches the OS" | "ready-to-use, just sign in" |

**Remember:** ask who manages the operating system. If you do, it's IaaS. If the provider does and you bring your own app, it's PaaS.

### CapEx vs OpEx

| | Capital expense (CapEx) | Operating expense (OpEx) |
|---|---|---|
| What it is | Upfront purchase of assets you own | Ongoing payment for a service you consume |
| Timing | Large payment before use | Billed per period, after use |
| Accounting | Depreciated over years | Expensed as consumed |
| Capacity | Forecast and buy for the peak | Spend follows real demand |
| Exam cue | "buy servers", "build a datacenter" | "pay monthly for what you used", "no upfront cost" |

**Remember:** owning hardware is CapEx. Renting cloud resources on the consumption model is OpEx.

### Scalability vs elasticity

| | Scalability | Elasticity |
|---|---|---|
| What it is | The ability to add or remove resources | Adding and removing resources automatically as demand changes |
| Who starts it | Someone making a planned change | The platform, responding live to load |
| Fits | Known, planned growth | Unpredictable spikes |
| Exam cue | "able to grow", "scale up or out" | "automatically add resources to meet demand" |

**Remember:** elasticity is scalability that runs itself. If nobody has to press a button, it's elasticity.

### Vertical vs horizontal scaling

| | Vertical scaling | Horizontal scaling |
|---|---|---|
| Also called | Scale up / scale down | Scale out / scale in |
| What changes | CPU and memory of one resource | The number of identical resources |
| Example | Resize one VM to a larger size | Add more VMs to share the load |
| Exam cue | "a more powerful server" | "add more identical servers" |

**Remember:** bigger machine is up. More machines is out.

### Public vs private vs hybrid cloud

| | Public cloud | Private cloud | Hybrid cloud |
|---|---|---|---|
| What it is | Provider-owned hardware shared by many organizations | Hardware used by one organization only | Public and private connected together |
| Upfront cost | Lowest | Highest | In between |
| Control | Least | Most | Balanced |
| Use it when | Fast start, low cost, large scale | Strict compliance or data-residency rules | Sensitive systems stay private, the rest or seasonal peaks go public |
| Exam cue | "no hardware to buy", "shared" | "dedicated", "single organization" | "keep some systems private while using the public cloud" |

**Remember:** hybrid needs both halves connected. Two separate environments that never share workloads are not hybrid.

## Domain 2: Describe Azure architecture and services

### Regions vs availability zones vs region pairs

| | Region | Availability zone | Region pair |
|---|---|---|---|
| What it is | One or more datacenters in a geographic area on a low-latency network | A physically separate datacenter group inside a region, with its own power, cooling, and networking | Two regions in the same geography, far apart, linked for recovery |
| Protects against | Nothing by itself; it is where you deploy | Loss of one datacenter in the region | Loss of an entire region |
| Use it when | Choosing location by latency, features, price, or compliance | You need high availability inside one region | You need disaster recovery across regions |
| Exam cue | "where resources physically run" | "physically separate datacenters within a region" | "replicate to another region", "regional outage" |

**Remember:** zones protect you inside a region. Only a second region protects you from losing the region.

### Virtual machines vs containers vs Azure Functions

| | Azure Virtual Machines | Containers (ACI, AKS) | Azure Functions |
|---|---|---|---|
| What it is | A full cloud computer (IaaS) | An app packaged with its dependencies, sharing the host OS | Event-driven serverless code |
| You manage | The OS and all software on it | The app and its container | Only your code |
| Billing | For the time the VM runs | For the container resources | Per execution; idle costs little or nothing |
| Use it when | Full control, custom setup, lift and shift | Portable apps and microservices | Short tasks triggered by an upload, message, or timer |
| Exam cue | "control the operating system" | "portable", "orchestrate containers" (AKS) | "serverless", "pay per execution" |

**Remember:** a VM is always on and fully yours to manage. A function runs only when triggered and has no server for you to see.

### Blob access tiers: hot vs cool vs cold vs archive

| | Hot | Cool | Cold | Archive |
|---|---|---|---|---|
| Access pattern | Frequent | Infrequent, kept at least about 30 days | Rarer, longer minimum retention | Rarely accessed, long-term |
| Storage cost | Highest | Lower | Lower still | Lowest |
| Access cost | Lowest | Higher | Higher | Highest |
| Reading data | Immediate | Immediate | Immediate | Offline; retrieval takes hours |
| Exam cue | "active data" | "infrequently accessed" | "rarely accessed" | "cheapest", "compliance records", "can wait to retrieve" |

**Remember:** as storage gets cheaper, reading gets more expensive. Archive is the only tier you cannot read straight away.

### LRS vs ZRS vs GRS vs GZRS

| | LRS | ZRS | GRS | GZRS |
|---|---|---|---|---|
| Where copies live | Three copies in one datacenter | Across three availability zones in one region | Primary region plus the paired secondary region | Zones in the primary region plus the secondary region |
| Survives | Disk or server failure | A zone (datacenter) failure | A full regional outage | A zone failure and a regional outage |
| Exam cue | "lowest cost" | "survive a datacenter failure" | "protect against a region outage" | "highest durability" |

**Remember:** anything without a G stays in one region. For a regional outage, pick GRS or GZRS.

### Azure VPN Gateway vs Azure ExpressRoute

| | Azure VPN Gateway | Azure ExpressRoute |
|---|---|---|
| What it is | Encrypted site-to-site tunnel into a VNet | Private, dedicated connection into Azure |
| Uses the public internet | Yes | No |
| Performance | Varies with internet conditions | Consistent and predictable |
| Use it when | Linking an office or branch at low cost | Moving large or sensitive workloads with strict requirements |
| Exam cue | "encrypted over the internet" | "private connection not over the internet" |

**Remember:** encryption does not make a VPN private. If the question rules out the internet, it's ExpressRoute.

## Domain 3: Describe Azure management and governance

### Azure Policy vs Azure RBAC vs resource locks

| | Azure Policy | Azure RBAC | Resource locks |
|---|---|---|---|
| What it is | Rules evaluated against resource properties | Role assignments that grant permissions | A guardrail on a resource, group, or subscription |
| Controls | What configurations are allowed | Who can perform which actions | Whether anyone can delete or modify it |
| Applies to | Every deployment in the assigned scope | The assigned user, group, or app | Everyone, whatever their role |
| Use it when | Only allow approved regions, require tags | Let a user view but not change resources | Stop a production database being deleted by mistake |
| Exam cue | "enforce rules", "deny non-compliant resources" | "least privilege", "assign roles" | "prevent accidental deletion" |

**Remember:** RBAC decides who, Policy decides what, and a lock blocks the action for everyone until it's removed.

### Pricing Calculator vs TCO Calculator vs Microsoft Cost Management

| | Pricing Calculator | TCO Calculator | Microsoft Cost Management |
|---|---|---|---|
| What it is | Estimator for planned Azure services | Comparison of on-premises cost against Azure | Reporting and control of real Azure spend |
| When | Before deployment | Before migration | After deployment |
| Data source | Configurations you enter | Your description of the current datacenter | Actual usage in your subscriptions |
| Key features | Service picker, monthly estimate | Multi-year side-by-side comparison | Cost analysis, budgets, alerts |
| Exam cue | "estimate before deploying" | "compare on-premises with Azure", "business case" | "monitor actual spend", "budget alert" |

**Remember:** if the resources don't exist yet, it's a calculator. If they're already running, it's Cost Management.

### Azure Advisor vs Azure Service Health vs Azure Monitor

| | Azure Advisor | Azure Service Health | Azure Monitor |
|---|---|---|---|
| What it is | Personalized best-practice recommendations | Personalized view of Azure platform events | Full-stack telemetry platform |
| Question it answers | How can I improve my resources? | Is an Azure problem affecting me? | How are my apps and resources behaving? |
| Covers | Cost, security, reliability, operational excellence, performance | Service issues, planned maintenance, health advisories | Metrics and logs, with Log Analytics, alerts, and Application Insights |
| Exam cue | "recommendations", "resize an underused VM" | "Azure outage affecting my services" | "query logs", "alert on CPU", "app response times" |

**Remember:** Advisor gives advice, Service Health reports on Azure itself, and Monitor measures your own workloads.

### Microsoft Defender for Cloud vs Microsoft Purview

| | Microsoft Defender for Cloud | Microsoft Purview |
|---|---|---|
| What it is | Security posture management and workload protection | Unified data governance and compliance |
| Focuses on | How securely resources are configured, and threats against them | What data you hold, where it lives, and how sensitive it is |
| Key features | Secure score, recommendations, threat alerts | Data catalog, classification, lineage and discovery |
| Exam cue | "secure score", "threat detection" | "catalog data", "classify sensitive data" |

**Remember:** Defender for Cloud protects your resources. Purview helps you understand and govern your data.

### CanNotDelete vs ReadOnly locks

| | CanNotDelete | ReadOnly |
|---|---|---|
| Read | Allowed | Allowed |
| Modify | Allowed | Blocked |
| Delete | Blocked | Blocked |
| Use it when | Normal changes are fine but deletion must not happen | The configuration must be frozen |

**Remember:** "prevent accidental deletion" alone means CanNotDelete. ReadOnly also stops changes.

[← Back to the study guide](README.md)
