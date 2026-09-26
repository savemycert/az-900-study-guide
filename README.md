# AZ-900 Study Guide: Microsoft Certified: Azure Fundamentals

A free, open study guide for the **Microsoft Certified: Azure Fundamentals (AZ-900)** exam: revision notes for every domain, side-by-side comparisons of commonly confused services, a glossary, 20 worked sample questions, and the official syllabus as a checklist with a full free lesson for every topic.

Maintained by [SaveMyCert](https://www.savemycert.com/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide), where you can read every lesson free, [practice with explained questions](https://www.savemycert.com/practice/azure-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide) and [take timed mock exams](https://www.savemycert.com/mocks/azure-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide).

## Contents

- [Exam at a glance](#exam-at-a-glance)
- [Exam domains](#exam-domains)
- [What is in this repo](#what-is-in-this-repo)
- [Syllabus checklist](#syllabus-checklist)
  - [Domain 1: Describe cloud concepts](#domain-1-describe-cloud-concepts)
  - [Domain 2: Describe Azure architecture and services](#domain-2-describe-azure-architecture-and-services)
  - [Domain 3: Describe Azure management and governance](#domain-3-describe-azure-management-and-governance)
- [How to study for AZ-900](#how-to-study-for-az-900)
- [Sample questions](sample-questions.md)
- [Free resources](#free-resources)

## Exam at a glance

| | |
|---|---|
| Exam code | AZ-900 |
| Level | Foundational |
| Questions | 40–60 |
| Time limit | 45 min |
| Passing score | 700 / 1000 |
| Format | Multiple choice & more |
| Exam fee | $99 (US; varies by country) |
| Valid for | Does not expire |

Exam details change. Always confirm them in the official [Microsoft AZ-900 study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/az-900) from Microsoft Learn.

## Exam domains

| # | Domain | Weight | Topics |
|---|---|---|---|
| 1 | [Describe cloud concepts](#domain-1-describe-cloud-concepts) | 28% | 3 |
| 2 | [Describe Azure architecture and services](#domain-2-describe-azure-architecture-and-services) | 38% | 4 |
| 3 | [Describe Azure management and governance](#domain-3-describe-azure-management-and-governance) | 34% | 4 |

That is 3 domains and 11 topics. Spend your time in proportion to the weights: the heaviest domain decides more of your score than the lightest.

Microsoft publishes each weight as a range (for example 25–30%). The figures here fall within those ranges, adjusted to add up to 100%.

## What is in this repo

| File | What it gives you |
|---|---|
| [Domain 1 notes](notes/domain-1-describe-cloud-concepts.md) | Describe cloud concepts: condensed revision notes per topic |
| [Domain 2 notes](notes/domain-2-describe-azure-architecture-and-services.md) | Describe Azure architecture and services: condensed revision notes per topic |
| [Domain 3 notes](notes/domain-3-describe-azure-management-and-governance.md) | Describe Azure management and governance: condensed revision notes per topic |
| [Commonly confused services](comparisons.md) | Side-by-side tables of the services questions set against each other |
| [Glossary](glossary.md) | Every in-scope term and service in one sentence |
| [Sample questions](sample-questions.md) | 20 worked questions with answers and reasoning |
| [Exam-day guide](exam-day-guide.md) | Booking, testing options, scoring, results and retakes |

## Syllabus checklist

Tick each topic off once you can explain it without notes. The "Must know" facts are the ones questions turn on. Each lesson link goes to the complete, free lesson.

### Domain 1: Describe cloud concepts

**Weight: 28%.** Cloud computing fundamentals: cloud models, the benefits of cloud services, and the IaaS/PaaS/SaaS service types. Official weighting 25–30%.

📝 Revision notes: [Domain 1: Describe cloud concepts](notes/domain-1-describe-cloud-concepts.md)

- [ ] **Describe cloud computing**
  <br>Define cloud computing; the shared responsibility model; cloud models — public, private, and hybrid — and appropriate use cases for each; the consumption-based model; comparing cloud pricing models; serverless.
  - 📖 Lesson: [What Is Cloud Computing? An Azure AZ-900 Guide](https://www.savemycert.com/revision/azure-fundamentals/what-is-cloud-computing-azure/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)
  - Must know: Cloud computing is the on-demand delivery of compute, storage, and networking over the internet, paid for on a pay-as-you-go basis.
  - Must know: The consumption-based model means you pay only for the resources you use, with no large up-front purchase and no charge for idle capacity.
- [ ] **Describe the benefits of using cloud services**
  <br>The benefits of high availability and scalability in the cloud; the benefits of reliability and predictability; the benefits of security and governance; the benefits of manageability in the cloud.
  - 📖 Lesson: [Benefits of Cloud Services: An Azure AZ-900 Guide](https://www.savemycert.com/revision/azure-fundamentals/benefits-of-cloud-services-azure/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)
  - Must know: High availability keeps applications running with minimal downtime, backed by provider service-level agreements (SLAs).
  - Must know: Scalability adds or removes resources to meet demand: vertical scaling changes one resource's power (scale up/down), while horizontal scaling changes the number of resources (scale out/in).
- [ ] **Describe cloud service types**
  <br>Infrastructure as a service (IaaS), platform as a service (PaaS), and software as a service (SaaS); identifying appropriate use cases for each cloud service type.
  - 📖 Lesson: [IaaS vs PaaS vs SaaS: Cloud Service Types Explained](https://www.savemycert.com/revision/azure-fundamentals/iaas-paas-saas-azure/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)
  - Must know: The three cloud service types are IaaS, PaaS, and SaaS; moving up the ladder, the provider manages more and you manage less.
  - Must know: IaaS rents infrastructure and gives you the most control; you manage the operating system and everything above it.

### Domain 2: Describe Azure architecture and services

**Weight: 38%.** Azure's core architectural components and its compute, networking, storage, and identity/access/security services. Official weighting 35–40%.

📝 Revision notes: [Domain 2: Describe Azure architecture and services](notes/domain-2-describe-azure-architecture-and-services.md)

- [ ] **Describe the core architectural components of Azure**
  <br>Azure regions, region pairs, and sovereign regions; availability zones; Azure datacenters; Azure resources and resource groups; subscriptions; management groups; the hierarchy of resource groups, subscriptions, and management groups.
  - 📖 Lesson: [Azure Regions, Availability Zones & Resource Hierarchy](https://www.savemycert.com/revision/azure-fundamentals/azure-regions-availability-zones-architecture/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)
  - Must know: A region is a group of datacenters in one area; regions belong to geographies, and you choose a region when you deploy.
  - Must know: Region pairs join two regions hundreds of miles apart for disaster recovery and replication; sovereign regions like Azure Government are isolated for compliance.
- [ ] **Describe Azure compute and networking services**
  <br>Comparing compute types — containers, virtual machines, and functions; virtual machine options including Azure Virtual Machines, Virtual Machine Scale Sets, availability sets, and Azure Virtual Desktop; the resources required for virtual machines; application hosting options — web apps, containers, and virtual machines; virtual networking — the purpose of Azure virtual networks, subnets, peering, Azure DNS, Azure VPN Gateway, and ExpressRoute; public and private endpoints.
  - 📖 Lesson: [Azure Compute & Networking Services Explained](https://www.savemycert.com/revision/azure-fundamentals/azure-compute-networking-services/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)
  - Must know: Compute options trade control for convenience: virtual machines give the most control, containers add portability, and Azure Functions need the least management.
  - Must know: Azure Functions is serverless and event-driven, and you pay per execution, so idle code costs almost nothing.
- [ ] **Describe Azure storage services**
  <br>Comparing Azure Storage services; storage tiers; redundancy options; storage account options and storage types; options for moving files — AzCopy, Azure Storage Explorer, and Azure File Sync; migration options — Azure Migrate and Azure Data Box.
  - 📖 Lesson: [Azure Storage Services, Tiers & Redundancy: AZ-900](https://www.savemycert.com/revision/azure-fundamentals/azure-storage-services/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)
  - Must know: Azure Blob Storage is object storage for unstructured data (images, video, backups); Azure Files is managed SMB/NFS file shares; Queue Storage is messaging; Table Storage is NoSQL key-value; Disk Storage provides virtual machine disks.
  - Must know: Blob access tiers trade storage cost against access cost: hot (frequent), cool (infrequent), cold (rare), and archive (rarely accessed, cheapest to store, with an hours-long retrieval latency).
- [ ] **Describe Azure identity, access, and security**
  <br>Directory services — Microsoft Entra ID and Microsoft Entra Domain Services; authentication methods — single sign-on (SSO), multifactor authentication (MFA), and passwordless; external identities; Microsoft Entra Conditional Access; Azure role-based access control (RBAC); the concept of Zero Trust; the defense-in-depth model; the purpose of Microsoft Defender for Cloud.
  - 📖 Lesson: [Azure Identity, Access & Security: AZ-900 Guide](https://www.savemycert.com/revision/azure-fundamentals/azure-identity-access-security/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)
  - Must know: Microsoft Entra ID is Azure's cloud identity and directory service — formerly named Azure Active Directory (Azure AD) — that stores accounts and verifies sign-ins; Microsoft Entra Domain Services adds managed, traditional domain features like domain join and Kerberos.
  - Must know: Authentication methods include single sign-on (sign in once for many apps), multi-factor authentication (two or more factors for strong protection), and passwordless (replacing the password with the Authenticator app, Windows Hello, or a security key).

### Domain 3: Describe Azure management and governance

**Weight: 34%.** Cost management, governance and compliance tooling, resource deployment and management tools, and monitoring. Official weighting 30–35%.

📝 Revision notes: [Domain 3: Describe Azure management and governance](notes/domain-3-describe-azure-management-and-governance.md)

- [ ] **Describe cost management in Azure**
  <br>Factors that can affect costs in Azure; the pricing calculator; cost management capabilities in Azure; the purpose of tags.
  - 📖 Lesson: [Azure Cost Management: Estimate, Monitor, and Reduce Cloud Spend](https://www.savemycert.com/revision/azure-fundamentals/azure-cost-management/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)
  - Must know: Azure costs depend on resource type, usage, region, network egress, and subscription or billing type.
  - Must know: Use the Pricing Calculator to estimate the cost of Azure services before you deploy them.
- [ ] **Describe features and tools in Azure for governance and compliance**
  <br>The purpose of Microsoft Purview in Azure; the purpose of Azure Policy; the purpose of resource locks.
  - 📖 Lesson: [Azure Governance and Compliance: Purview, Policy, and Resource Locks](https://www.savemycert.com/revision/azure-fundamentals/azure-governance-compliance-policy/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)
  - Must know: Microsoft Purview provides unified data governance and compliance through data cataloging, classification, and discovery across your estate.
  - Must know: Azure Policy enforces organizational rules on resources, using effects like audit (flag) and deny (block non-compliant resources).
- [ ] **Describe features and tools for managing and deploying Azure resources**
  <br>The Azure portal; Azure Cloud Shell, Azure CLI, and Azure PowerShell; the purpose of Azure Arc; infrastructure as code (IaC); Azure Resource Manager (ARM) and ARM templates.
  - 📖 Lesson: [Azure Management and Deployment Tools: Portal, CLI, PowerShell, Arc and IaC](https://www.savemycert.com/revision/azure-fundamentals/azure-management-deployment-tools/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)
  - Must know: The Azure portal is the web-based graphical interface (GUI) for managing Azure and building dashboards; best for learning and one-off changes.
  - Must know: Azure Cloud Shell is a browser-based shell, already authenticated, that comes preloaded with the Azure CLI and Azure PowerShell.
- [ ] **Describe monitoring tools in Azure**
  <br>The purpose of Azure Advisor; Azure Service Health; Azure Monitor, including Log Analytics, Azure Monitor alerts, and Azure Monitor Application Insights.
  - 📖 Lesson: [Azure Monitoring Tools: Advisor, Service Health and Azure Monitor](https://www.savemycert.com/revision/azure-fundamentals/azure-monitoring-tools-advisor-monitor/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)
  - Must know: Azure Advisor gives personalized recommendations across five categories: cost, security, reliability, operational excellence, and performance.
  - Must know: Azure Service Health tells you whether an Azure service issue, planned maintenance, or health advisory is affecting your specific resources, unlike the generic public Azure status page.

## How to study for AZ-900

1. **Read the lesson for each topic** in the checklist above, starting with the heaviest domain. Every lesson is free on the [AZ-900 revision notes](https://www.savemycert.com/revision/azure-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide).
2. **Practice straight after reading.** Answer [AZ-900 practice questions](https://www.savemycert.com/practice/azure-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide) on the topic you just read. Each option comes with an explanation of why it is right or wrong.
3. **Review what you got wrong**, re-read that lesson section, and tick the topic off only when you get its questions right.
4. **Take a full-length [AZ-900 mock exam](https://www.savemycert.com/mocks/azure-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)** under the real time limit. Aim to pass mocks comfortably before you book.
5. **On the last day**, skim the [AZ-900 cheat sheet](https://www.savemycert.com/cheat-sheet/azure-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide) instead of starting anything new.

## Sample questions

[sample-questions.md](sample-questions.md) has 20 worked AZ-900 questions with the answer, why each option is right or wrong, and the reasoning steps.

## Free resources

- [Microsoft AZ-900 study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/az-900): the official source (Microsoft Learn)
- [AZ-900 certification overview](https://www.savemycert.com/certifications/azure-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)
- [AZ-900 revision notes](https://www.savemycert.com/revision/azure-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide): every lesson, free to read
- [AZ-900 practice questions](https://www.savemycert.com/practice/azure-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide): with an explanation on every option
- [AZ-900 mock exams](https://www.savemycert.com/mocks/azure-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide): full-length and timed
- [AZ-900 cheat sheet](https://www.savemycert.com/cheat-sheet/azure-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide): the key facts on one page
- [All certification study guides](https://github.com/savemycert/certification-study-guides)

## Contributing

Spotted an error or an out-of-date fact? [Open an issue](../../issues) with the topic and a link to the official source. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License and disclaimer

This guide is licensed under [CC BY 4.0](LICENSE). You can reuse and adapt it, including commercially, as long as you credit **SaveMyCert** with a link to https://www.savemycert.com/.

This is an independent study resource. It is not affiliated with or endorsed by Microsoft Learn. Microsoft Certified: Azure Fundamentals and AZ-900 are trademarks of their respective owner. Exam domains and weights are taken from the official exam guide linked above.
