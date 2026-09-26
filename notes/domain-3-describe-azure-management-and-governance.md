# Domain 3: Describe Azure management and governance (34%)

This domain covers the tools that estimate and control spend, enforce rules and protect resources, deploy and manage resources, and monitor what is running. Questions are mostly recognition: a need is described and you choose the one tool built for it.

## Describe cost management in Azure

- **What drives cost:**

| Factor | Effect |
|---|---|
| Resource type | Each service is metered differently; bigger sizes and higher tiers cost more |
| Usage | You pay for run time and for data stored and accessed |
| Region | The same service can be priced differently per region |
| Network traffic | Outbound transfer (egress) is generally billed; inbound usually is not |
| Subscription type | Pay-as-you-go, Enterprise Agreement, free or student offers carry different rates and terms |

- **Three cost tools, three moments:**
  - **Pricing Calculator:** before deployment. You enter planned services and settings (size, region, OS, hours, quantity) and get an estimated monthly total. Nothing has to exist in your subscription.
  - **TCO Calculator:** before migration. You describe your current on-premises estate (servers, storage, networking, power, labor, software) and compare its multi-year cost with Azure. Built for business cases.
  - **Microsoft Cost Management:** after deployment. Reports real spend from your subscription.
- **Cost Management features:**
  - **Cost analysis:** slice spend by service, resource group, region, subscription, or tag, and watch trends.
  - **Budgets:** a spend threshold on a scope.
  - **Alerts:** notifications (email or action groups) as spend nears or passes a budget. Budgets notify; they do not stop resources.
- **Ways to pay less:**
  - **Azure Reservations:** a discount for committing to a specific resource (for example, a VM size) for 1 or 3 years.
  - **Azure savings plans:** a discount for committing to a fixed hourly compute spend for 1 or 3 years; more flexible, since the discount follows usage across eligible services and sizes.
  - **Azure Spot Virtual Machines:** spare capacity at a deep discount that Azure can **evict** when it needs it back. For interruptible work such as batch jobs.
  - **Azure Hybrid Benefit:** reuse existing on-premises Windows Server or SQL Server licenses in Azure.
  - Practices: right-size, autoscale, shut down idle resources, choose cheaper regions or tiers where suitable.
- **Tags:** name-value labels (for example `costcenter = marketing`) on resources, resource groups, and subscriptions. They do not change behavior. Their cost job is to let you group and report spend by team, project, or environment.
- **Traps:**
  - "Estimate before deploying" is the Pricing Calculator. "Compare on-premises with Azure" is the TCO Calculator. Mixing them is the classic mistake.
  - Anything about resources that already exist (actual spend, budgets, alerts) is Cost Management.
  - Spot VMs are cheap but can disappear. Never pick them for critical always-on services.

📖 Full lesson: [Azure Cost Management: Estimate, Monitor, and Reduce Cloud Spend](https://www.savemycert.com/revision/azure-fundamentals/azure-cost-management/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

## Describe features and tools in Azure for governance and compliance

- **Governance** = controls that keep the environment in line with your rules. **Compliance** = being able to show that you meet those rules and outside regulations.
- **Three tools, three targets:** Purview governs data, Azure Policy governs resource configuration, and resource locks protect individual resources.
- **Microsoft Purview:** unified data governance and compliance across your estate, including on-premises and other clouds.
  - Data catalog: a searchable map of data sources.
  - Data classification: scan and label sensitive content such as personal or financial data.
  - Data discovery: explore lineage and how data moves between systems.
  - Cues: "catalog", "classify sensitive data", "data governance".
- **Azure Policy:** evaluates resources against rules automatically.
  - **Audit** effect: report non-compliant resources without blocking them.
  - **Deny** effect: stop a non-compliant resource from being created or updated.
  - Classic examples: allow only approved regions; require a tag on every resource.
  - Group policies into **initiatives** and assign them at management group, subscription, or resource group scope.
- **Policy vs RBAC:**

| | Azure RBAC | Azure Policy |
|---|---|---|
| Controls | Who can act | What configuration is allowed |
| Evaluates | Identity and assigned role | Properties of the resource |
| Example | Alice can create VMs | New VMs must be in an approved region |

- A user with full RBAC rights can still be blocked by a policy. The two apply together.
- **Resource locks:** stop accidental deletion or change. Set on a subscription, resource group, or resource, and they apply to everyone regardless of role. The lock must be removed before the blocked action can happen.

| Lock | Read | Modify | Delete |
|---|---|---|---|
| CanNotDelete | Yes | Yes | No |
| ReadOnly | Yes | No | No |

- **Traps:**
  - "Prevent accidental deletion" is a lock (CanNotDelete), not RBAC or Policy.
  - ReadOnly blocks changes as well as deletion. Choose it only when the resource must not change at all.
  - Purview is about data. Policy is about resources. Do not swap them.

📖 Full lesson: [Azure Governance and Compliance: Purview, Policy, and Resource Locks](https://www.savemycert.com/revision/azure-fundamentals/azure-governance-compliance-policy/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

## Describe features and tools for managing and deploying Azure resources

- **Azure portal:** web-based GUI for creating and managing resources by pointing and clicking, plus customizable **dashboards**. Best for learning, exploring, and one-off changes. Weak for repeating the same setup many times.
- **Azure Cloud Shell:** a browser-based shell opened from the portal, already signed in, with a **Bash** or **PowerShell** experience. The Azure CLI and Azure PowerShell come preinstalled. No local install needed.
- **Azure CLI vs Azure PowerShell:** both cross-platform (Windows, macOS, Linux), both script and automate the same tasks; they differ in style.

| | Azure CLI | Azure PowerShell |
|---|---|---|
| Form | Commands starting with `az` | Modules of Verb-Noun cmdlets |
| Example | `az group create` | `New-AzResourceGroup` |
| Suits | Bash and cross-platform scripting | PowerShell and Windows automation |

- Cloud Shell is where you run commands. The CLI and PowerShell are the command sets.
- **Azure Arc:** brings resources that run outside Azure (on-premises servers, other clouds, edge) under Azure management, giving one **control plane**. Connected resources can be put in resource groups, tagged, governed with policies, and seen in the portal while they keep running where they are. Supports servers, Kubernetes clusters, and some data services. Cues: "hybrid", "multicloud", "manage on-premises servers from Azure".
- **Infrastructure as code (IaC):** define infrastructure in files, store them like code, and deploy them. **Declarative** (describe the end state) and **repeatable** (the same file produces the same environment).
- **Azure Resource Manager (ARM):** the service that receives every create or change request, whatever tool sent it.
  - **ARM templates:** JSON files that declare resources for ARM to deploy.
  - **Bicep:** a simpler, more readable language that compiles to ARM JSON.
- **Traps:**
  - Arc manages resources that live outside Azure. It is not a deployment tool for Azure itself.
  - CLI and PowerShell have the same capabilities. Choose by background, not features.
  - Bicep does not replace ARM. It sits on top of it.

📖 Full lesson: [Azure Management and Deployment Tools: Portal, CLI, PowerShell, Arc and IaC](https://www.savemycert.com/revision/azure-fundamentals/azure-management-deployment-tools/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

## Describe monitoring tools in Azure

- **Azure Advisor:** free, personalized recommendations for resources you already have, in five categories: **Cost, Security, Reliability, Operational excellence, Performance**. Example: resize an underused VM. It advises; it does not report outages or show live metrics.
- **Azure Service Health:** a personalized view of Azure platform events that affect the services and regions you use.
  - **Service issues:** active problems in Azure now.
  - **Planned maintenance:** upcoming work that may affect you.
  - **Health advisories:** changes needing action, such as a feature retirement.
  - You can set alerts on these events. The public **Azure status page** shows global health for everyone and is not tailored to you.
- **Azure Monitor:** the full-stack platform for collecting and analyzing telemetry from your own apps and infrastructure.
  - **Metrics:** numeric values over time (CPU percentage, request counts).
  - **Logs:** detailed event records you search and analyze.
- **Components of Azure Monitor:**
  - **Log Analytics:** query log data stored in a Log Analytics workspace using **Kusto Query Language (KQL)**.
  - **Azure Monitor alerts:** a rule on a metric or log condition fires an **action group** (email, SMS, push, webhook, automation).
  - **Application Insights:** application performance monitoring (APM) for web apps: response times, failure rates, request volumes, dependencies, usage.

| Question | Tool |
|---|---|
| How can I improve cost, security, or reliability of my resources? | Azure Advisor |
| Is an Azure outage or maintenance affecting me? | Azure Service Health |
| How are my apps and resources behaving? | Azure Monitor |
| Where do I query logs? | Log Analytics (KQL) |
| Why is my web app slow or failing? | Application Insights |

- **Traps:**
  - Advisor recommends. Monitor measures. Service Health reports on Azure itself.
  - Log Analytics, alerts, and Application Insights are all part of Azure Monitor, not separate products you choose instead of it.
  - A problem with Azure's platform points to Service Health. A problem inside your own application points to Application Insights.

📖 Full lesson: [Azure Monitoring Tools: Advisor, Service Health and Azure Monitor](https://www.savemycert.com/revision/azure-fundamentals/azure-monitoring-tools-advisor-monitor/?utm_source=github&utm_medium=readme&utm_campaign=az-900-study-guide)

[← Back to the study guide](../README.md)
