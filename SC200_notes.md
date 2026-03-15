# Microsoft SC-200: Security Operations Analyst Study Notes & Practice Questions

## Exam Overview

The **SC-200: Microsoft Security Operations Analyst** exam validates skills in:
- Mitigating threats using **Microsoft 365 Defender** (25–30%)
- Mitigating threats using **Microsoft Defender for Cloud** (15–20%)
- Mitigating threats using **Microsoft Sentinel** (50–55%)

---

## Domain 1 – Mitigate Threats Using Microsoft 365 Defender

### Key Concepts

- **Microsoft 365 Defender** is an integrated XDR (Extended Detection and Response) solution covering: Microsoft Defender for Endpoint, Defender for Office 365, Defender for Identity, and Defender for Cloud Apps.
- **Incidents** aggregate related alerts across all Microsoft 365 Defender products.
- **Threat Analytics** provides reports on active threat actors and campaigns.
- **Advanced Hunting** uses Kusto Query Language (KQL) to search across 30 days of raw data.
- **Secure Score** measures an organization's security posture.
- **Attack Simulation Training** (in Defender for Office 365) tests users against phishing and social engineering simulations.

### Microsoft Defender for Endpoint (MDE)

- Onboarding methods: Group Policy, SCCM, Intune, local script, VDI script.
- **Device risk levels**: Informational, Low, Medium, High.
- **Live Response** allows running scripts and commands on remote endpoints.
- **Automated Investigation and Remediation (AIR)**: reduces analyst workload by automatically investigating and remediating alerts.
- **Threat and Vulnerability Management (TVM)**: identifies CVEs on devices, provides remediation recommendations.
- **Network Protection**: blocks connections to malicious/low-reputation domains (requires Windows 10 1709+).
- **Controlled Folder Access**: protects against ransomware by restricting write access to protected folders.
- **Attack Surface Reduction (ASR) rules**: block behaviors commonly used by malware.

### Microsoft Defender for Office 365 (MDO)

- **Plan 1**: Safe Attachments, Safe Links, anti-phishing policies.
- **Plan 2**: Adds Threat Trackers, Threat Explorer, Attack Simulation Training, and AIR.
- **Safe Attachments** policy actions: Block, Dynamic Delivery, Replace.
- **Safe Links** rewrites URLs and checks them at click-time.
- **Zero-Hour Auto Purge (ZAP)** retroactively moves malicious email already delivered to a user's Inbox.
- **Threat Explorer** (real-time) vs **Threat Tracker** (trend data) are Plan 2 features.
- **Submissions**: admins/users can submit FP/FN emails to Microsoft for analysis.

### Microsoft Defender for Identity (MDI)

- Monitors **Active Directory Domain Controllers** and **AD FS servers** for suspicious activity.
- Sensors installed directly on domain controllers (agentless via network traffic capture).
- Detects: Pass-the-Hash, Pass-the-Ticket, Golden Ticket, DCSync, LDAP enumeration, Brute Force.
- Integrates with Microsoft 365 Defender portal for unified incident view.
- **Lateral Movement Paths (LMPs)** visualize how attackers could move to sensitive accounts.

### Microsoft Defender for Cloud Apps (MDCA)

- Provides **Cloud Discovery**, **Cloud App Catalog**, **Conditional Access App Control**, **Information Protection**, and **Threat Protection**.
- **Cloud Discovery**: analyzes traffic logs to identify sanctioned/unsanctioned cloud apps (Shadow IT).
- **App Connectors** (API-based): enable deeper visibility into O365, Salesforce, Box, AWS, etc.
- **Session Policies**: use Conditional Access App Control proxy to monitor/block sessions in real-time.
- **Anomaly Detection policies**: impossible travel, activity from infrequent countries, mass download.
- **App Governance** add-on: monitors OAuth app behavior and permissions.

---

## Domain 1 – Practice Questions

**Q1.** A security analyst needs to investigate a phishing email that was delivered to a user's mailbox before the Safe Links policy was updated. Which Microsoft Defender for Office 365 feature should the analyst use to remove the email retroactively?

- A) Threat Explorer
- B) Zero-Hour Auto Purge (ZAP)
- C) Safe Attachments
- D) Attack Simulation Training

**Answer: B**
*ZAP retroactively detects and moves malicious messages already delivered to user mailboxes.*

---

**Q2.** You are configuring Microsoft Defender for Endpoint and need to prevent users from accessing known malicious websites. Which feature should you enable?

- A) Controlled Folder Access
- B) Attack Surface Reduction rules
- C) Network Protection
- D) Tamper Protection

**Answer: C**
*Network Protection blocks outbound connections to malicious/low-reputation hosts at the network level.*

---

**Q3.** An analyst suspects an attacker is using a Golden Ticket attack in the environment. Which Microsoft security product is BEST suited to detect this activity?

- A) Microsoft Defender for Endpoint
- B) Microsoft Defender for Cloud Apps
- C) Microsoft Defender for Identity
- D) Microsoft Defender for Office 365

**Answer: C**
*MDI is designed to detect Kerberos-based attacks including Golden Ticket, Silver Ticket, and DCSync against Active Directory.*

---

**Q4.** A company wants to identify unsanctioned cloud applications being used by employees. Which Microsoft Defender for Cloud Apps feature provides this capability?

- A) Session Policies
- B) Cloud Discovery
- C) App Connectors
- D) Conditional Access App Control

**Answer: B**
*Cloud Discovery analyzes firewall and proxy traffic logs to detect shadow IT (unsanctioned cloud apps).*

---

**Q5.** In Microsoft 365 Defender, which query language is used for Advanced Hunting?

- A) SQL
- B) SPL (Splunk Processing Language)
- C) KQL (Kusto Query Language)
- D) XQL

**Answer: C**
*Advanced Hunting in Microsoft 365 Defender uses KQL to query raw security data.*

---

**Q6.** You need to automatically investigate and remediate alerts in Microsoft Defender for Endpoint to reduce manual workload. Which feature should you configure?

- A) Live Response
- B) Automated Investigation and Remediation (AIR)
- C) Threat and Vulnerability Management
- D) Advanced Hunting

**Answer: B**
*AIR automatically investigates alerts and can remediate threats without analyst involvement.*

---

**Q7.** Which Microsoft Defender for Office 365 feature allows you to test users' responses to simulated phishing campaigns?

- A) Threat Explorer
- B) Safe Attachments
- C) Attack Simulation Training
- D) Threat Trackers

**Answer: C**
*Attack Simulation Training (Plan 2 feature) enables running simulated phishing and social engineering campaigns.*

---

**Q8.** A user receives an email with a malicious attachment. Safe Attachments is configured with the "Dynamic Delivery" action. What happens to the email?

- A) The email is blocked and never delivered.
- B) The email body is delivered immediately; the attachment is replaced with a placeholder and reattached after scanning.
- C) The email and attachment are quarantined.
- D) The attachment is deleted, and the email body is delivered.

**Answer: B**
*Dynamic Delivery sends the email body right away with a placeholder attachment, then delivers the original attachment after it passes scanning — minimizing delivery delay.*

---

**Q9.** Which Microsoft 365 Defender feature provides a unified view of security posture across an organization and recommends improvement actions?

- A) Secure Score
- B) Threat Analytics
- C) Advanced Hunting
- D) Incidents

**Answer: A**
*Microsoft Secure Score measures the organization's security posture and provides actionable recommendations.*

---

**Q10.** You want to prevent ransomware from encrypting files in common user folders such as Documents and Desktop. Which Defender for Endpoint feature should you enable?

- A) Network Protection
- B) Attack Surface Reduction rules
- C) Controlled Folder Access
- D) Tamper Protection

**Answer: C**
*Controlled Folder Access restricts which applications can write to protected folders, blocking ransomware encryption attempts.*

---

## Domain 2 – Mitigate Threats Using Microsoft Defender for Cloud

### Key Concepts

- **Microsoft Defender for Cloud** (formerly Azure Security Center + Azure Defender) provides CSPM (Cloud Security Posture Management) and CWPP (Cloud Workload Protection Platform).
- **Secure Score**: measures adherence to security controls; higher score = better posture.
- **Defender Plans**: enable enhanced threat protection for Azure resources (VMs, SQL, Storage, Containers, App Service, Key Vault, DNS, ARM, Kubernetes).
- **Just-In-Time (JIT) VM Access**: reduces attack surface by opening management ports only when needed, for a limited time.
- **Adaptive Application Controls**: whitelisting of approved applications running on VMs.
- **Adaptive Network Hardening**: hardens NSG rules based on actual traffic patterns.
- **Regulatory Compliance dashboard**: maps controls to standards (PCI DSS, ISO 27001, NIST, CIS).
- **Workflow Automation**: triggers Logic Apps based on security alerts/recommendations.
- **Data export**: stream alerts and recommendations to Log Analytics, Event Hubs, or partner SIEMs.
- **Multi-cloud support**: protects AWS (via AWS connector) and GCP workloads in addition to Azure.
- **Security alerts** are generated by Defender plans; they can be exported to Microsoft Sentinel.

### Alert Severity Levels

| Severity | Meaning |
|----------|---------|
| High | Confirmed malicious activity; immediate action required |
| Medium | Suspicious activity; investigation recommended |
| Low | Benign positive, potential vulnerability |
| Informational | Context for other alerts |

### Defender for Cloud Key Integrations

- **Microsoft Sentinel**: ingest Defender for Cloud alerts as incidents.
- **Microsoft Defender for Endpoint**: integrated agent for VM threat protection.
- **Azure Policy**: used to enforce security recommendations at scale.
- **Log Analytics workspace**: stores security data for analysis.

---

## Domain 2 – Practice Questions

**Q11.** A security team wants to reduce the attack surface on Azure VMs by ensuring that RDP and SSH ports are only open when needed. Which Defender for Cloud feature should they use?

- A) Adaptive Application Controls
- B) Adaptive Network Hardening
- C) Just-In-Time VM Access
- D) Workflow Automation

**Answer: C**
*JIT VM Access closes management ports by default and opens them on-demand for a specified duration and approved IP range.*

---

**Q12.** You want Microsoft Defender for Cloud to automatically trigger a Logic App whenever a high-severity alert is generated. Which feature enables this?

- A) Data Export
- B) Regulatory Compliance
- C) Workflow Automation
- D) Secure Score

**Answer: C**
*Workflow Automation in Defender for Cloud can trigger Azure Logic Apps in response to alerts or recommendations.*

---

**Q13.** A company needs to monitor security posture across Azure, AWS, and GCP resources from a single dashboard. Which product provides this capability?

- A) Microsoft Sentinel
- B) Microsoft Defender for Cloud
- C) Microsoft 365 Defender
- D) Microsoft Defender for Endpoint

**Answer: B**
*Defender for Cloud supports multi-cloud environments (Azure, AWS, GCP) and provides unified CSPM across all three.*

---

**Q14.** An analyst sees a Defender for Cloud alert with severity "High" for a VM. What does this severity indicate?

- A) The alert is purely informational.
- B) The activity is suspicious but unconfirmed.
- C) The alert represents confirmed malicious activity requiring immediate action.
- D) The alert is a false positive.

**Answer: C**
*High-severity alerts indicate confirmed malicious activity and require immediate investigation and remediation.*

---

**Q15.** You need to ensure that only approved applications run on a set of Azure VMs. Which Defender for Cloud feature provides this capability?

- A) Just-In-Time VM Access
- B) Adaptive Application Controls
- C) Adaptive Network Hardening
- D) Regulatory Compliance

**Answer: B**
*Adaptive Application Controls build allowlists of known legitimate applications and alert when unlisted applications run.*

---

**Q16.** Your organization wants to assess its compliance with PCI DSS using Microsoft Defender for Cloud. Where should the analyst look?

- A) Secure Score
- B) Security Alerts
- C) Regulatory Compliance dashboard
- D) Recommendations

**Answer: C**
*The Regulatory Compliance dashboard in Defender for Cloud maps your environment's controls against standards like PCI DSS, ISO 27001, and NIST.*

---

**Q17.** A security engineer wants to stream Defender for Cloud alerts to an external SIEM. Which feature supports this?

- A) Workflow Automation
- B) Continuous Export / Data Export
- C) Just-In-Time VM Access
- D) Adaptive Network Hardening

**Answer: B**
*Continuous Export (Data Export) allows streaming of alerts and recommendations to Log Analytics, Event Hubs, or partner SIEMs.*

---

## Domain 3 – Mitigate Threats Using Microsoft Sentinel

### Key Concepts

- **Microsoft Sentinel** is a cloud-native SIEM (Security Information and Event Management) and SOAR (Security Orchestration, Automation, and Response) solution built on Azure.
- Deployed inside a **Log Analytics workspace**.
- Data is ingested using **Data Connectors** (300+ connectors available).
- **Analytics Rules** generate **Incidents** from raw log data.
- **Workbooks** provide visualization dashboards.
- **Playbooks** are **Azure Logic Apps** used for automated response (SOAR).
- **Hunting queries** allow proactive threat hunting using KQL.
- **Notebooks** integrate with Azure Machine Learning for advanced analysis.
- **Entities** (users, hosts, IPs, URLs) are extracted from alerts and incidents for enrichment.
- **UEBA (User and Entity Behavior Analytics)**: detects anomalous behavior baselines.
- **Threat Intelligence**: ingestion of IOCs (Indicators of Compromise) via TI connectors or manual upload (STIX/TAXII).
- **Watchlists**: CSV-based reference lists used to enrich alerts or suppress false positives.
- **Content Hub**: centralized location to install solution packages (connectors, rules, workbooks, playbooks).
- **Repositories**: connect Sentinel workspace to a Git repository for CI/CD of content (as-code).

### Analytics Rule Types

| Rule Type | Description |
|-----------|-------------|
| Scheduled | KQL query runs on a schedule; generates alert if results match threshold |
| Microsoft Security | Auto-creates incidents from other Microsoft security product alerts |
| Fusion | ML-based correlation across multiple data sources to detect multi-stage attacks |
| ML Behavior Analytics | Built-in ML detection (anomalous SSH/RDP login) |
| Threat Intelligence | Matches IOCs from TI feeds against log data |
| Near Real-Time (NRT) | Runs every minute for near-real-time detection |

### Data Connectors

- **Microsoft services**: direct integration via Service-to-Service (S2S) connectors (e.g., Azure AD, Office 365, Microsoft 365 Defender, Defender for Cloud).
- **CEF (Common Event Format)**: syslog-based connector for network appliances (firewalls, proxies).
- **Syslog**: generic Linux syslog connector.
- **REST API / Azure Functions**: for custom data sources.
- **Log Analytics Agent** (MMA/AMA): deploys to Windows/Linux machines for log collection.
- **Azure Monitor Agent (AMA)**: modern replacement for MMA; uses **Data Collection Rules (DCRs)**.

### KQL Key Operators (for Advanced Hunting & Analytics Rules)

```kql
// Filter rows
SecurityEvent | where EventID == 4625

// Count events
SecurityEvent | summarize count() by Account

// Time filtering
SigninLogs | where TimeGenerated > ago(1d)

// Join tables
SecurityAlert
| join kind=inner (SecurityIncident) on AlertName

// Project specific columns
AzureActivity | project TimeGenerated, Caller, OperationName

// Extend (add calculated column)
SecurityEvent | extend AccountDomain = split(Account, "\\")[0]

// Top N results
SecurityEvent | top 10 by TimeGenerated desc

// Parse JSON fields
SecurityEvent | extend ParsedData = parse_json(EventData)

// Regex extraction
SecurityEvent | where Account matches regex "admin.*"
```

### Incident Management

- **Incident lifecycle**: New → Active → Closed (True Positive / False Positive / Benign Positive / Undetermined).
- **Incident tasks**: structured checklist steps for SOC analysts.
- **Entities**: automatically extracted from alerts (users, IPs, hosts, URLs, file hashes).
- **Investigation graph**: visualizes relationships between entities in an incident.
- **Similar incidents**: Sentinel automatically surfaces similar historical incidents.
- **Comments**: analysts can add notes to incidents for collaboration.

### Playbooks (SOAR)

- Based on **Azure Logic Apps**.
- Triggered by: alert creation, incident creation, or manually.
- Common automations: block IP in firewall, disable user in Azure AD, send Teams/email notification, create ServiceNow ticket.
- Must have the **Microsoft Sentinel Responder** role (or higher) to run playbooks on incidents.
- **Automation Rules**: trigger playbooks or auto-assign/close incidents based on conditions — evaluated before Analytics Rules run.

### UEBA

- Must be enabled per workspace.
- Produces **User/Entity behavior scores** and **Anomaly tables** (BehaviorAnalytics, UserAccessAnalytics).
- Can sync identities from Azure AD and on-prem AD.
- **Investigation priority score**: ranks users and entities by risk.

### Threat Intelligence in Sentinel

- Ingest via **Threat Intelligence – TAXII** connector (pull from STIX/TAXII 2.x servers).
- Ingest via **Threat Intelligence Platforms** connector (push via Microsoft Graph Security TI API).
- IOCs stored in **ThreatIntelligenceIndicator** table.
- **Analytics rule type "Threat Intelligence"** auto-matches IOCs against ingested logs.
- View and manage TI in **Threat Intelligence blade** in Sentinel.

---

## Domain 3 – Practice Questions

**Q18.** A SOC analyst needs to automatically block a malicious IP address in the firewall whenever a high-severity incident is created in Microsoft Sentinel. What should the analyst configure?

- A) Analytics Rule
- B) Workbook
- C) Playbook triggered by an Automation Rule
- D) Hunting Query

**Answer: C**
*Playbooks (Logic Apps) handle automated response actions. An Automation Rule can trigger a playbook automatically when an incident is created.*

---

**Q19.** You need to create a detection rule in Microsoft Sentinel that runs a KQL query every 5 minutes to detect brute-force attacks in near real-time. Which analytics rule type should you use?

- A) Fusion
- B) Scheduled
- C) Near Real-Time (NRT)
- D) ML Behavior Analytics

**Answer: C**
*NRT (Near Real-Time) rules run approximately every minute and are designed for low-latency detection scenarios.*

---

**Q20.** An analyst wants to detect multi-stage attacks that span multiple Microsoft security products and data sources using machine learning. Which Sentinel analytics rule type should be used?

- A) Scheduled
- B) Microsoft Security
- C) Threat Intelligence
- D) Fusion

**Answer: D**
*Fusion uses machine learning to correlate signals across multiple data sources and products to detect complex multi-stage attacks (e.g., credential theft followed by lateral movement).*

---

**Q21.** You are ingesting logs from a network firewall that supports CEF format into Microsoft Sentinel. Which data connector type should you use?

- A) Syslog
- B) CEF (Common Event Format)
- C) REST API
- D) Azure Monitor Agent

**Answer: B**
*CEF is the correct connector for network appliances (firewalls, proxies) that output logs in Common Event Format.*

---

**Q22.** A security analyst wants to search for threat hunting queries in Microsoft Sentinel and run them across historical data. Which Sentinel feature should the analyst use?

- A) Analytics Rules
- B) Watchlists
- C) Hunting
- D) Workbooks

**Answer: C**
*The Hunting feature in Sentinel allows analysts to proactively run KQL queries across ingested data to find threats.*

---

**Q23.** You want to suppress false positive incidents in Microsoft Sentinel where a specific user triggers an alert during scheduled maintenance windows. Which feature is BEST suited for this?

- A) Automation Rules
- B) Watchlists
- C) UEBA
- D) Threat Intelligence

**Answer: A**
*Automation Rules can suppress or auto-close incidents based on conditions (e.g., entity, time window) — ideal for maintenance window suppression.*

---

**Q24.** An analyst needs to visualize trends in security events over time in Microsoft Sentinel. Which feature should be used?

- A) Incidents
- B) Workbooks
- C) Hunting
- D) Playbooks

**Answer: B**
*Workbooks provide interactive dashboards and visualizations of security data in Microsoft Sentinel.*

---

**Q25.** You need to ingest threat intelligence indicators (IOCs) from a TAXII 2.1 server into Microsoft Sentinel. Which connector should you configure?

- A) Threat Intelligence Platforms
- B) Microsoft 365 Defender
- C) Threat Intelligence – TAXII
- D) Syslog

**Answer: C**
*The "Threat Intelligence – TAXII" connector pulls IOCs from STIX/TAXII 2.x servers into the ThreatIntelligenceIndicator table in Sentinel.*

---

**Q26.** A Sentinel playbook needs to disable a compromised user account in Azure Active Directory when an incident is created. What Azure service powers Sentinel playbooks?

- A) Azure Functions
- B) Azure Logic Apps
- C) Azure Automation Runbooks
- D) Azure Data Factory

**Answer: B**
*Sentinel playbooks are built on Azure Logic Apps, which provide the workflow engine for SOAR automation.*

---

**Q27.** You want to include a list of known VIP user accounts in Microsoft Sentinel to enrich alerts involving those accounts. Which Sentinel feature is BEST suited for this?

- A) UEBA
- B) Threat Intelligence
- C) Watchlists
- D) Bookmarks

**Answer: C**
*Watchlists allow importing CSV data (e.g., VIP user lists, IP allowlists) that can be referenced in KQL queries to enrich or filter alerts.*

---

**Q28.** A security analyst is investigating an incident in Sentinel and wants to visually see how different entities (users, IPs, hosts) are related. Which feature should they use?

- A) Hunting Bookmarks
- B) Workbooks
- C) Investigation Graph
- D) Notebooks

**Answer: C**
*The Investigation Graph provides an interactive visualization of relationships between entities involved in a Sentinel incident.*

---

**Q29.** You want to automatically assign newly created incidents to a specific analyst and change their severity based on conditions. Which Sentinel feature handles this without creating a playbook?

- A) Analytics Rules
- B) Automation Rules
- C) Fusion Rules
- D) Workbooks

**Answer: B**
*Automation Rules can automatically assign incidents, change severity, add tags, and trigger playbooks — without needing a full Logic App playbook for simple actions.*

---

**Q30.** A company uses Microsoft Sentinel and wants to detect anomalous sign-in behavior for users based on behavioral baselines. Which Sentinel feature provides this?

- A) Threat Intelligence
- B) Fusion
- C) User and Entity Behavior Analytics (UEBA)
- D) Watchlists

**Answer: C**
*UEBA builds behavioral baselines for users and entities and detects deviations that may indicate compromise.*

---

**Q31.** An analyst writes the following KQL query in Microsoft Sentinel:

```kql
SecurityEvent
| where EventID == 4625
| summarize FailedLogins = count() by Account, bin(TimeGenerated, 1h)
| where FailedLogins > 10
```

What is this query detecting?

- A) Successful logins
- B) Accounts with more than 10 failed login attempts within any 1-hour window
- C) Accounts with more than 10 successful logins
- D) Login events from the past 10 hours

**Answer: B**
*EventID 4625 is "An account failed to log on." The query counts failed logins per account per hour and filters for accounts with more than 10 failures — classic brute-force detection.*

---

**Q32.** You need to onboard Microsoft Defender for Cloud alerts into Microsoft Sentinel. Which data connector should you use?

- A) Azure Active Directory
- B) Microsoft Defender for Cloud
- C) Office 365
- D) Microsoft 365 Defender

**Answer: B**
*The "Microsoft Defender for Cloud" data connector in Sentinel ingests Defender for Cloud security alerts as incidents.*

---

**Q33.** A SOC manager wants Microsoft Sentinel to automatically generate incidents from Microsoft Defender for Endpoint alerts without writing custom KQL. Which analytics rule type achieves this?

- A) Fusion
- B) Scheduled
- C) Microsoft Security
- D) NRT

**Answer: C**
*The "Microsoft Security" analytics rule type auto-creates Sentinel incidents from alerts generated by Microsoft security products, including MDE, MDO, MDI, and MDCA.*

---

**Q34.** Which table in Microsoft Sentinel stores ingested threat intelligence indicators (IOCs)?

- A) SecurityAlert
- B) ThreatIntelligenceIndicator
- C) SecurityIncident
- D) CommonSecurityLog

**Answer: B**
*ThreatIntelligenceIndicator is the dedicated table where imported IOCs (IPs, domains, file hashes, URLs) are stored in Sentinel.*

---

**Q35.** An analyst saved interesting events during a threat hunt as bookmarks. Where can these bookmarks be reviewed as part of a formal investigation?

- A) Analytics Rules
- B) Incidents (by promoting bookmarks to an incident or adding to existing incident)
- C) Workbooks
- D) Watchlists

**Answer: B**
*Hunting bookmarks can be promoted to a new incident or added to an existing incident for formal investigation tracking.*

---

## Quick Reference: Common KQL Tables in Sentinel

| Table | Contents |
|-------|---------|
| SecurityEvent | Windows Security Event Log (e.g., logins, process creation) |
| SigninLogs | Azure AD interactive sign-in logs |
| AADNonInteractiveUserSignInLogs | Azure AD non-interactive sign-ins |
| AuditLogs | Azure AD audit events |
| OfficeActivity | Microsoft 365 activity (SharePoint, Teams, Exchange) |
| AzureActivity | Azure subscription-level activity (ARM operations) |
| SecurityAlert | Alerts from Microsoft security products |
| SecurityIncident | Sentinel incidents |
| ThreatIntelligenceIndicator | Ingested IOCs |
| CommonSecurityLog | CEF-format logs (firewalls, proxies) |
| Syslog | Linux syslog events |
| BehaviorAnalytics | UEBA user/entity risk scores |
| DeviceEvents | MDE device events (Advanced Hunting) |
| DeviceProcessEvents | MDE process creation events |
| DeviceNetworkEvents | MDE network connection events |
| DeviceFileEvents | MDE file creation/modification events |
| EmailEvents | MDE/MDO email events |
| CloudAppEvents | MDCA cloud app activity |

---

## Common Exam Tips

1. **Sentinel is built on Log Analytics**: all data lives in a Log Analytics workspace; all queries use KQL.
2. **Playbooks = Logic Apps**: whenever a question mentions automated response/SOAR in Sentinel, the answer usually involves playbooks (Logic Apps).
3. **Automation Rules vs Playbooks**: Automation Rules handle simple actions (assign, close, change severity, suppress) without a Logic App. Playbooks are needed for complex external actions (block IP, disable user).
4. **Fusion rules cannot be customized**: they are read-only ML-based detections managed by Microsoft.
5. **NRT rules are near-real-time, not truly real-time**: NRT rules run approximately every minute (not continuously), so a small detection delay exists.
6. **Microsoft Security rules ≠ custom KQL**: they auto-convert alerts from Microsoft products; no KQL needed.
7. **JIT VM Access** is a Defender for Cloud feature, not a network-level feature.
8. **ZAP** only works for Exchange Online, not on-premises Exchange.
9. **MDI** monitors domain controllers — it must be installed on every DC.
10. **CEF vs Syslog**: use CEF connector for appliances that format logs in CEF; use Syslog connector for generic Linux logs.
11. **Watchlists** are referenced in KQL with `_GetWatchlist('watchlistAlias')`.
12. **Defender Secure Score** is separate from **Sentinel** — Secure Score lives in the Microsoft 365 Defender portal and Defender for Cloud.
