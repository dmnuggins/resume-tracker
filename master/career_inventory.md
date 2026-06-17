# Career Inventory

<!--
  SOURCE DOCUMENT — NEVER SUBMITTED
  This file is the raw material for all resume variants.
  - Pull bullets from here when building or refining a variant.
  - Add new achievements, projects, and skills here as they happen.
  - Be specific: include tools, scope, and measurable outcomes where possible.
  - Do not sanitize for length — that happens in the variant.
-->

---

## Skills Evidence

| Skill                                | Where Demonstrated                                                         |
| ------------------------------------ | -------------------------------------------------------------------------- |
| Endpoint management (Intune/Jamf)    | VCA — Endpoint & Device Management; iKrusher — Endpoint Management         |
| Active Directory / Entra ID          | VCA — Identity & Access; The Flex Company — Identity & Access              |
| VDI & virtualization (Citrix/VMware) | VCA — VDI & Virtualization                                                 |
| PowerShell scripting & automation    | VCA — Scripting & Automation                                               |
| Microsoft 365 administration         | iKrusher — Microsoft 365                                                   |
| Networking (LAN/WAN, VPN, firewall)  | iKrusher — Networking                                                      |
| Security & compliance                | VCA — Security                                                             |
| Vendor & ISP coordination            | iKrusher — Vendor & ISP Coordination                                       |
| Data architecture & reporting        | Five Acres — Data Tools & Reporting                                        |
| Documentation & end-user training    | Five Acres — Documentation & Training; The Flex Company — End User Support |
| Cost optimization                    | The Flex Company — Cost Optimization                                       |
| Backup & disaster recovery           | The Flex Company — Data & Backup                                           |

---

## VCA Consultants — IT Technician II

_May 2024 – Present_

### Networking

- Assisted with core network switch upgrades + rewiring with DAC
- Configured virtual NICs for Dell EMC ESXi hosts when setting up a new server
- Configured Fortinet firewall rules to enable service connectivity for department needs
  - Air quality management dashboard
  - USPS stamp machine verification
  - Isolated Python dev machine on a guest network
  - VLAN + physical port management for desktop and IoT setup

### Endpoint & Device Management

- Managed 20+ Windows endpoints in Intune with policy compliance applied across all remote users
- Deployed and imaged devices using [process/tool], reducing provisioning time from [X] to [Y]
- Maintained hardware inventory and lifecycle records for 100+ endpoints across 3 sites
  - Orange
  - LA
  - Denver

### VDI & Virtualization

- Administered VMWare/Omnissa virtual desktop environment serving 120 concurrent users
- Troubleshot VDI session issues including DEM profile corruption and Horizon connection latency; cut help desk requests for authentication and profile problems from several per day to a few per week
- Coordinated and executed the migration of VDI infrastructure from Windows 10 to 11
- Horizon connection server upgrades
- Maintained instant clone pool updates through master machines deployed in Horizon
- Deployed VDI to 10ZiG thin clients, centrally managed through a 10ZiG management server for patching and remote support

### Identity & Access

- Managed user lifecycle (provisioning, de-provisioning, role changes) in Active Directory and Entra ID for 120+ accounts
- Enforced least-privilege access across Active Directory and SaaS apps; reviewed group memberships quarterly
- Configured and maintained SSO/MFA/Conditional Access policies for SaaS applications
  - Zoom
  - Bluebeam
  - GitHub Teams + GitLab
  - Ajera (ERP)

### Application management

- Worked with department and team leads to vet applications before systems integration
- Tested, configured, and integrated applications to function well on our VDI infrastructure (master machine to instant clone deployment, DEM configs, FSLogix)
- Maintained regular software updates (could there be automation here?)

### Scripting & Automation

- Wrote PowerShell scripts to automate [task, e.g. account provisioning, report generation], saving 3 hours/week
- Wrote a Python/pyautogui script that cycles CALog and PC Tracker dashboards on networked displays; keeps them self-sustaining and eliminated manual recasting
- Built a PowerShell script that generates anonymous share links across 200,000+ items, reading from a client address list to produce the right link for each utility and benchmarking subfolder <!-- NEEDS DETAIL: This appears to describe the same project as the SharePoint migration + Python/Graph API bullet below — one says PowerShell, the other says Python. Clarify or remove the duplicate -->
- Documented and handed off [N] automation scripts to the team knowledge base
- Used Claude Code to research approaches, audit existing scripts, and build new automation
  - Peer-reviewed all AI-assisted code before production use, even for internal tooling
- Used Omnissa DEM to deploy PowerShell scripts for pre-login configuration, registry injections, and cache resets
- Migrated 200,000+ building files to SharePoint using Microsoft's migration agent on a dedicated sync VM, then built a Python script to generate anonymous share links so the Benchmarking team could distribute the right links to each building client
  - Python + Microsoft Graph API

### Security

- Used Darktrace to monitor and triage security incidents; tuned behavioral parameters to reduce false positives while keeping effective threat detection in place
- Maintained endpoint security through Omnissa Horizon instant clone deployment, Microsoft Defender, and a third-party security agent for malware detection
- Re-enrolled BYOD endpoints from mergers and acquisitions into Intune and deployed ScreenConnect for fast remote admin access
- Assisted with user audit and litigation hold for a structural project under contention <!-- NEEDS DETAIL: What did you specifically do (eDiscovery, export, freeze)? What systems (M365, Exchange)? What was the project context? -->

### Projects

- Led/contributed to [project name]: [what it was], [your role], [outcome]
- Migrated [system/service] from [X] to [Y], coordinating with [teams] and completing within [timeline]

---

## iKrusher — IT Systems Administrator

_Feb 2024 – May 2024_

### Networking

- Managed LAN/WAN infrastructure across 2 sites, including switches, routers, and firewall (e.g. HP Aruba, Dell EMC hosts, TrueNAS storage)
- Configured and maintained secure remote access to internal desktop + server VM's for remote users using Horizon View + DUO authentication
- Troubleshot connectivity and throughput issues <!-- NEEDS DETAIL: What caused the issues? Any specific resolution or outcome? -->

### Microsoft 365

- Administered Microsoft 365 tenant for 56 users: Exchange Online, SharePoint, Teams, and licensing
- Implemented [policy/feature, e.g. DLP, retention policies, shared mailbox governance]
- Onboarded users to M365 and wrote documentation and runbooks that cut future onboarding time by 30 minutes

### Endpoint Management

- Managed 50+ endpoints (Windows/macOS) in Intune with baseline configuration policies
- Standardized device build process, reducing setup time per device from [X] to [Y]
-

### Vendor & ISP Coordination

- Served as primary contact for vendors and ISPs; owned tickets, SLAs, and escalations on issues affecting end users

---

## The Flex Company — IT & Operations Coordinator

_Nov 2020 – Jul 2022_

### Data & Backup

- Designed and maintained backup strategy for our creative assets
  - Creative files lived on a local NAS backed by Amazon S3 and Glacier for redundancy and long-term storage
- Migrated company files from a shared G-Drive folder to Google Workspace Shared Drives; 10,000+ records moved with no data loss
- Documented backup and recovery procedures, ratified by VP of Business Operations

### Identity & Access

- Managed user accounts and access across Google Workspace, Slack, Asana, etc. for 30+ users
- Implemented an access review process that cut stale accounts and communication channels by 20% on average

### Cost Optimization

- Audited SaaS subscriptions and identified unnecessary resource usage on GCloud account, saving $4,000/year
- Worked with the Head of Business to renegotiate our office maintenance contract, cutting cost 15% with no drop in service level

### End User Support

- Provided Tier 1–2 support for 20+ staff across a hybrid remote environment
- Built internal knowledge base <!-- NEEDS DETAIL: What tool (Confluence, Notion, SharePoint)? What topics/scope? How many staff used it? -->

---

## Five Acres — Data Architect

_Apr 2018 – Jul 2019_

### Web Development

- Extended an internally hosted web app that used regex to parse and clean child incident report data, streamlining the research team's intake workflow

### Data Tools & Reporting

- Built a Power BI dashboard that gave leadership visibility into departmental budgets

### Documentation & Training

- Wrote inline code comments and supplemental documentation covering the web app's deployment and maintenance
- Trained staff on Welligent web app navigation, troubleshooting, and best practices

---

## Five Acres — IT Tech

_Jul 2017 – Apr 2018_

_Promoted to Data Architect Apr 2018_

### End User Support

- Handled IT support for hardware, software, and business apps in a healthcare environment with strict compliance requirements
  - Rolled out BitLocker across 150+ Windows machines with IT leads in 2 business days, staggering mobile and stationary PCs to minimize downtime
- Onboarded new staff, ran training sessions, and covered day-to-day troubleshooting

### Identity & Access

- Managed Active Directory accounts and handled application access requests via the IT service desk

### Infrastructure & Security

- Set up and maintained secure remote access; kept endpoint security controls applied and current
- Supported disk encryption rollout and applied compliance-driven system updates <!-- NEEDS DETAIL: This overlaps with the BitLocker bullet above — consider merging or clarifying if there were additional encryption initiatives beyond BitLocker -->
