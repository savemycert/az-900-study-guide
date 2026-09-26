# AZ-900 Sample Questions with Answers

5 worked practice questions for the **Microsoft Certified: Azure Fundamentals (AZ-900)** exam. Try each one before you open the answer.

For many more, with the same explanation on every option, use the [AZ-900 practice questions](https://www.savemycert.com/practice/azure-fundamentals/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide) on SaveMyCert.

## Question 1

*Describe cloud concepts*

**Which statement best defines cloud computing?** Choose one.

- **a.** The delivery of computing services such as compute, storage, and networking over the internet on a pay-as-you-go basis
- **b.** Buying and installing physical servers in your own room and maintaining them yourself
- **c.** A single application that stores files only on a local hard drive
- **d.** A high-speed internet connection sold by a telecommunications company

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ This captures the core definition: on-demand delivery of compute, storage, and networking over the internet, paid as you use it.
- **b** ❌ This describes a traditional on-premises datacenter, which is what cloud computing replaces.
- **c** ❌ Local file storage on one device is not cloud computing, which delivers shared resources over the internet.
- **d** ❌ Connectivity alone is not cloud computing; the cloud provides compute, storage, and networking resources you rent on demand.

**The concept.** Cloud computing is the on-demand delivery of computing services over the internet.

**Why this is correct.** The correct answer names the three service categories (compute, storage, networking) delivered over the internet on a pay-as-you-go basis, which is the exam definition. Buying and running your own servers is on-premises, not cloud; a local-only app and an internet connection are neither the delivery of rentable resources nor pay-as-you-go.

**How to reason it out**

1. Recall that cloud computing means renting technology rather than owning it.
2. Check that the answer mentions delivery of resources over the internet.
3. Confirm it includes the pay-as-you-go idea, which separates it from on-premises.

> **Exam tip:** Cloud computing is the on-demand delivery of compute, storage, and networking over the internet, paid for as you use it.

</details>

📖 Learn this topic: [What Is Cloud Computing? An Azure AZ-900 Guide](https://www.savemycert.com/revision/azure-fundamentals/what-is-cloud-computing-azure/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

---

## Question 2

*Describe Azure architecture and services*

**Which term describes one or more physically separate datacenters within a single Azure region, each with independent power, cooling, and networking?** Choose one.

- **a.** Availability zone
- **b.** Region pair
- **c.** Geography
- **d.** Resource group

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ An availability zone is one or more physically separate datacenters inside a region, each with its own power, cooling, and networking, so a single datacenter failure does not take down resources in another zone.
- **b** ❌ A region pair joins two separate regions hundreds of miles apart for disaster recovery, not separate datacenters within one region.
- **c** ❌ A geography is a larger grouping of regions used for data-residency and compliance, not the separate datacenters inside a single region.
- **d** ❌ A resource group is a logical container for resources; it has nothing to do with physical datacenter separation.

**The concept.** Availability zones are physically separate datacenters within one Azure region.

**Why this is correct.** An availability zone is defined as one or more physically separate datacenters in a region with independent power, cooling, and networking, so it protects against a single datacenter failing. A region pair is about two whole regions far apart, a geography is a broad grouping of regions, and a resource group is a logical (not physical) container, so none of those match the definition.

**How to reason it out**

1. Look for the trigger: physically separate datacenters inside one region.
2. Match that phrase to the availability zone definition.
3. Rule out region pair, geography, and resource group as different-scope concepts.

> **Exam tip:** Physically separate datacenters within a region equals availability zones.

</details>

📖 Learn this topic: [Azure Regions, Availability Zones & Resource Hierarchy](https://www.savemycert.com/revision/azure-fundamentals/azure-regions-availability-zones-architecture/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

---

## Question 3

*Describe Azure management and governance*

**Your team is planning a new solution and wants an estimated monthly cost of the Azure services before any resources are deployed. Which tool should you use?** Choose one.

- **a.** The Azure Pricing Calculator
- **b.** Microsoft Cost Management
- **c.** The Total Cost of Ownership (TCO) Calculator
- **d.** Azure Advisor

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ The Pricing Calculator estimates the cost of Azure services you configure by hand, so it is the right tool for projecting cost before deployment.
- **b** ❌ Cost Management reports on actual spend after resources are running; it cannot estimate a design that does not exist yet.
- **c** ❌ The TCO Calculator compares an on-premises environment with Azure; it is not used to price a specific set of planned Azure services.
- **d** ❌ Azure Advisor gives recommendations on existing resources; it does not build a pre-deployment cost estimate.

**The concept.** The Azure Pricing Calculator projects the cost of a proposed workload before it is deployed.

**Why this is correct.** The Pricing Calculator lets you add services and settings and returns an estimated monthly total, which is exactly what pre-deployment planning needs. Cost Management only reports real spend after deployment, the TCO Calculator answers the on-premises-versus-Azure question, and Advisor gives optimization recommendations on live resources, so none of those fit an estimate for a design that does not exist yet.

**How to reason it out**

1. Note the key phrase: estimate cost before deploying.
2. Match a pre-deployment estimate to the Pricing Calculator.
3. Rule out tools that need live resources or answer a different question.

> **Exam tip:** Estimate cost before deploying with the Azure Pricing Calculator.

</details>

📖 Learn this topic: [Azure Cost Management: Estimate, Monitor, and Reduce Cloud Spend](https://www.savemycert.com/revision/azure-fundamentals/azure-cost-management/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

---

## Question 4

*Describe cloud concepts*

**A company can create a virtual machine in Microsoft Azure in minutes and switch it off when it is no longer needed. Which characteristic of cloud computing does this describe?** Choose one.

- **a.** On-demand access to resources
- **b.** A capital expense
- **c.** A private deployment model
- **d.** Physical ownership of the datacenter

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ Requesting resources when needed and releasing them when done is exactly what on-demand access means.
- **b** ❌ A capital expense is a large up-front purchase of owned hardware, not the ability to turn resources on and off quickly.
- **c** ❌ A private cloud describes who uses the hardware, not the speed of provisioning resources on demand.
- **d** ❌ In the cloud the provider owns the datacenter; the customer does not own or house the hardware.

**The concept.** On-demand provisioning lets you start and stop resources quickly.

**Why this is correct.** Creating a resource in minutes and stopping it when done is the definition of on-demand access. A capital expense is about buying assets, a private model is about who shares the hardware, and datacenter ownership belongs to the provider, so none of those describe rapid provisioning.

**How to reason it out**

1. Identify the behavior: resources appear in minutes and stop when unused.
2. Match that behavior to on-demand access.
3. Eliminate options about cost type, deployment model, and ownership.

> **Exam tip:** Turning resources on in minutes and off when done is on-demand access, a hallmark of cloud computing.

</details>

📖 Learn this topic: [What Is Cloud Computing? An Azure AZ-900 Guide](https://www.savemycert.com/revision/azure-fundamentals/what-is-cloud-computing-azure/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

---

## Question 5

*Describe Azure architecture and services*

**An organization wants two Azure regions that are hundreds of miles apart so it can recover if one entire region suffers a major outage. Which Azure concept provides this?** Choose one.

- **a.** Region pair
- **b.** Availability zone
- **c.** Subscription
- **d.** Management group

<details>
<summary>Show answer and explanation</summary>

**Answer: a**

- **a** ✅ Region pairs join two regions in the same geography at least hundreds of miles apart, supporting disaster recovery and data replication if an entire region goes down.
- **b** ❌ Availability zones protect against a single datacenter failing inside one region, not against an entire region going down.
- **c** ❌ A subscription is a billing and access boundary, not a mechanism for regional disaster recovery.
- **d** ❌ A management group organizes multiple subscriptions; it does not provide geographic resilience.

**The concept.** Region pairs provide disaster recovery across two distant regions.

**Why this is correct.** A region pair links two regions hundreds of miles apart so a single large event is unlikely to affect both, which is exactly the region-outage protection described. Availability zones only cover a datacenter failure inside one region, while subscriptions and management groups are logical billing and organization boundaries, not resilience features.

**How to reason it out**

1. Identify the need: recovery from an entire region failing.
2. Recall that region pairs sit hundreds of miles apart for disaster recovery.
3. Reject availability zones (within-region) and the logical boundaries.

> **Exam tip:** Protection against a whole region failing points to region pairs.

</details>

📖 Learn this topic: [Azure Regions, Availability Zones & Resource Hierarchy](https://www.savemycert.com/revision/azure-fundamentals/azure-regions-availability-zones-architecture/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

---

[← Back to the AZ-900 study guide](README.md)
