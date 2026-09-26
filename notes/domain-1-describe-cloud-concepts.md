# Domain 1: Describe cloud concepts (28%)

This domain covers what cloud computing is, why organizations adopt it, and how the IaaS, PaaS, and SaaS service types divide work between you and the provider. Most questions give a short scenario or a key phrase and ask you to name the model, benefit, or service type it describes.

## Describe cloud computing

- **Cloud computing:** compute, storage, and networking delivered over the internet on demand. You rent capacity from a provider such as Microsoft Azure instead of buying and running your own hardware, and you release it when you no longer need it.
  - Compute = processing power (for example, virtual machines). Storage = files, databases, backups. Networking = the connections between them.
  - "On demand" means ready in minutes rather than the weeks a hardware purchase takes.
- **Consumption-based model:** you are billed for what you use, for as long as you use it. No upfront purchase and no charge for capacity you never requested.
  - Cues: "pay only for what you use", "pay-as-you-go", "no upfront cost".
  - Benefits: no need to guess capacity for your busiest day, lower waste, cheap experiments you can delete.
- **Serverless:** you supply code and the provider runs it when an event occurs, scales it automatically, and bills per execution. You never provision or manage servers. Azure Functions is the example (covered in Domain 2).

| | Capital expense (CapEx) | Operating expense (OpEx) |
|---|---|---|
| What you pay for | Physical assets you buy and own (servers, storage, network gear, the datacenter) | A service you consume |
| When you pay | A large sum before use | Per billing period, after use |
| Accounting | Depreciated over several years | Expensed as consumed |
| Capacity risk | You must forecast demand up front | Spend follows actual demand |
| Typical of | On-premises IT | Cloud computing |

- Adopting cloud moves the bulk of IT spend **from CapEx to OpEx**.
- **Shared responsibility model:** security and management duties are split between provider and customer. Neither side owns everything.

| Layer | IaaS | PaaS | SaaS |
|---|---|---|---|
| Physical datacenter, hosts, network | Provider | Provider | Provider |
| Operating system | Customer | Provider | Provider |
| Data, accounts and identities, devices | Customer | Customer | Customer |

- The middle layers move toward the provider as you go from IaaS to PaaS to SaaS. Your data and identities are **always** yours.
- **Deployment models** are about who uses and owns the hardware:

| | Public | Private | Hybrid |
|---|---|---|---|
| Hardware used by | Many organizations, logically isolated | One organization only | Both, connected |
| Owned by | The cloud provider | Your organization or a hosting partner | A combination |
| Upfront cost | Lowest | Highest | In between |
| Control | Least | Most | Balanced |
| Scale | Very high | Limited to your hardware | High |
| Choose when | Fast setup, low cost, rapid growth | Strict compliance, security, or data-residency rules | Keep sensitive systems private, use public cloud for the rest or for peaks |

- **Traps:**
  - "Pay only for what you use" describes the consumption model and OpEx, not a deployment model.
  - A private cloud does not have to sit in your own building. What makes it private is that one organization has the hardware to itself.
  - Hybrid means public and private connected so workloads and data can move between them. Two unrelated environments are not hybrid.
  - Customers never manage physical hosts or datacenters in any service type.

📖 Full lesson: [What Is Cloud Computing? An Azure AZ-900 Guide](https://www.savemycert.com/revision/azure-fundamentals/what-is-cloud-computing-azure/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

## Describe the benefits of using cloud services

- **High availability:** the application stays reachable with as little downtime as possible. You inherit it from the provider's infrastructure instead of buying duplicate hardware. Providers state expected availability in **service-level agreements (SLAs)**. Cue: "minimal downtime".
- **Scalability:** the ability to add or remove resources as demand changes.

| | Vertical scaling | Horizontal scaling |
|---|---|---|
| Also called | Scale up / scale down | Scale out / scale in |
| What changes | The size of one resource (CPU, memory) | How many resources there are |
| Example | Resize a VM to a bigger size | Add more identical VMs behind the app |
| Exam cue | "more CPU and memory for one server" | "add more identical servers" |

- **Elasticity:** scaling the platform performs **automatically**, adding and removing capacity live as load changes. Scalability is the capability; elasticity is the automatic response. Cue: "automatically add resources to meet demand", "unpredictable spikes".
- **Reliability:** the ability to recover from failures and keep working.
  - Fault tolerance: a standby component picks up the work when one breaks.
  - Disaster recovery: bringing the service back after a large outage, usually from another location.
- **Predictability** has two forms:
  - **Performance predictability:** a consistent user experience as load changes (scaling, load balancing).
  - **Cost predictability:** forecasting and tracking spend, possible because billing is metered (pricing calculators, cost analysis).
- **Security:** you build on the provider's investment in physical security, encryption options, and threat detection. How much security work you hand over depends on the service type.
- **Governance:** setting rules and enforcing them automatically across many resources (required tags, approved regions, configuration standards) and auditing compliance.
- **Manageability** is tested as two sides:

| Management **of** the cloud | Management **in** the cloud |
|---|---|
| The cloud manages resources for you | You manage the resources |
| Automatic scaling and recovery | Web portal |
| Deploying from templates | Command line and scripts |
| Monitoring health and performance | APIs |

- **Phrase-to-benefit map:** "minimal downtime" = high availability; "recover from a failure" = reliability; "forecast the monthly bill" = cost predictability; "enforce standards across resources" = governance.
- **Traps:**
  - Scaling that a person triggers is scalability, not elasticity.
  - High availability is about staying up. Reliability is about recovering. Questions that mention a second region or restoring after an outage lean toward reliability and disaster recovery.
  - Templates and automatic recovery are management *of* the cloud. The portal and CLI are management *in* the cloud.

📖 Full lesson: [Benefits of Cloud Services: An Azure AZ-900 Guide](https://www.savemycert.com/revision/azure-fundamentals/benefits-of-cloud-services-azure/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

## Describe cloud service types

- **The ladder:** IaaS, then PaaS, then SaaS. Each step up, the provider manages more of the stack and you manage less. The choice is control versus effort.
- **IaaS (Infrastructure as a Service):** you rent virtual machines, storage, and networking. The provider runs the hardware and virtualization host. You own the operating system upward: patching, configuration, runtimes, apps, data.
  - Most control, most work. Closest to running your own servers without the hardware.
  - Example: **Azure Virtual Machines**.
  - Use cases: lift and shift of existing servers, software that needs a specific OS setup, dev/test environments you create and destroy.
- **PaaS (Platform as a Service):** the provider also manages the OS, runtime, patching, and much of the scaling. You manage your application code and data.
  - Examples: **Azure App Service** (web apps and APIs), **Azure SQL Database** (managed database).
  - Use case: developers who want to ship an app or API without looking after servers.
- **SaaS (Software as a Service):** finished software you sign in to and use, usually by subscription. You manage your data, user access, and the settings the app exposes.
  - Examples: **Microsoft 365** (email, documents, collaboration), **Dynamics 365** (business apps such as CRM).

| | IaaS | PaaS | SaaS |
|---|---|---|---|
| Operating system | You | Provider | Provider |
| Runtime / middleware | You | Provider | Provider |
| Application | You | You | Provider |
| Your data | You | You | You |
| Control | Most | Medium | Least |
| Exam cue | "you manage the OS", "lift and shift" | "deploy your code, provider handles the OS" | "ready-to-use, just sign in" |

- **Fastest test:** ask who manages the operating system. You = IaaS. The provider = PaaS or SaaS. Then ask whether you are building your own app (PaaS) or just using finished software (SaaS).
- **Traps:**
  - A managed database with no OS patching is PaaS, not SaaS. You still own the data and the schema.
  - Azure Virtual Machines is IaaS even though Microsoft runs the hardware.
  - Data responsibility never moves entirely to the provider, even in SaaS.

📖 Full lesson: [IaaS vs PaaS vs SaaS: Cloud Service Types Explained](https://www.savemycert.com/revision/azure-fundamentals/iaas-paas-saas-azure/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

[← Back to the study guide](../README.md)
