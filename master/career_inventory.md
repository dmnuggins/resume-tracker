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
- Configured our internal 10ZiG thin client manager server to be able to connect to thin clients outside our network using a DMZ secure connection server to securely bridge external thin clients to our internal manager
- Configured virtual NICs for Dell EMC ESXi hosts when setting up a new server
- Configured Fortinet firewall rules to enable service connectivity for department needs
  - Air quality management dashboard
  - USPS stamp machine verification
  - Isolated Python dev machine on a guest network
  - VLAN + physical port management for desktop and IoT setup
- Managed LAN/WAN infrastructure across 3 sites (LA, Denver, Orange), including switches, routers, and firewall (e.g. HP Aruba, Dell EMC hosts, TrueNAS storage)
- Configured and maintained secure remote access to internal desktop + server VM's for remote users using Horizon View + DUO authentication
- Troubleshot connectivity and throughput issues with Horizon Client connections to server side VM's, ended up being a UAG bottleneck that resulted in lagging out our remote users

### Endpoint & Device Management

- Managed 20+ Windows endpoints in Intune with policy compliance applied across all remote users
- Maintained hardware inventory and lifecycle records for 100+ endpoints across 3 sites
  - Orange
  - LA
  - Denver
- Deployed ScreenConnect to enable comprehensive support for end user devices
- Deployed LAPS (Local Administrative Password Solution) to improve our security posture by conditionally auto-rotating stale passwords, moving away from manually configuring a local admin password
- Upgraded 10ZiG thin client fleet from 5000-series to 6000/7000-series hardware across multiple users
- Set up and imaged new laptops; handled Intune re-enrollment, license revocation from old devices, and full app stack installation (Bluebeam, O365, ScreenConnect/HelpWire)

### VDI & Virtualization

- Administered VMWare/Omnissa virtual desktop environment serving 120 concurrent users
- Troubleshot VDI session issues including Omnissa Dynamic Environment Manager profile corruption and Horizon connection latency; cut help desk requests for authentication and profile problems from several per day to a few per week
- Coordinated and executed the migration of VDI infrastructure from Windows 10 to 11
- Performed Horizon connection server upgrades
- Maintained instant clone pool image lifecycle across 7+ departmental pools (CAD, Structural, Green, IT, Admin, Code, Energy Modeler) — built and validated snapshots in vCenter on test pools before pushing to production
- Managed VDI application patching across all pools: Teams, FSLogix, VMware Tools, Horizon Client; used GPO-controlled update channels to suppress auto-updates in non-persistent environments
- Updated VMware ESXi hosts using vMotion to migrate live workloads without downtime; resolved a vGPU driver update failure on Host 10 via ESXi SSH CLI to unload the NVIDIA kernel module before remediation
- Deployed VDI to 10ZiG thin clients, centrally managed through a 10ZiG management server for patching and remote support
- Stabilized VDI for end users: reduced login/auth helpdesk requests from several per day to roughly once every 1.5 weeks by optimizing the login flow, DEM profile persistence, and FSLogix configuration
- Integrated git version control for DEM configurations to enable change auditing over time

### Identity & Access

- Managed user lifecycle (provisioning, de-provisioning, role changes) in Active Directory and Entra ID for 120+ accounts
- Enforced least-privilege access across Active Directory and SaaS apps; reviewed group memberships quarterly
- Configured and maintained SSO/MFA/Conditional Access policies for SaaS applications
  - Zoom
  - Bluebeam
  - GitHub Teams + GitLab
  - Ajera (ERP)
  - O365
- Coordinated cross-platform email standardization across AD, Entra ID, and SaaS apps (Autodesk, Bluebeam, Zoom, Ajera) ahead of Ajera SSO rollout — ensured all active accounts were consistent across local and cloud directories

### Application management

- Worked with department and team leads to vet applications before systems integration
- Tested, configured, and integrated applications to function well on VDI infrastructure (master machine to instant clone deployment, DEM configs, FSLogix)
- Diagnosed and resolved VDI application failures caused by DEM cache/profile corruption — including Revit add-ins (PyRevit, Scopbox) failing to load; resolved by clearing stale profile cache via DEM console
- Managed O365 license pool within 20-seat cap; swapped users between M365 tiers (with/without Teams) as team composition changed
- Deployed and configured Zoom Booking Pages for staff; stored booking URLs in AD extensionAttribute2 for dynamic attribution in the call routing system
- Maintained regular software updates across VDI image pools and managed endpoints

### Scripting & Automation

- Wrote and maintained PowerShell scripts for recurring IT tasks — including Active Directory user audits with terminated-user filtering, producing structured CSV reports for review
- Wrote a Python/pyautogui script that cycles CALog and PC Tracker dashboards on networked displays; keeps them self-sustaining and eliminated manual recasting
- Used Claude Code to research approaches, audit existing scripts, and build new automation
  - Peer-reviewed all AI-assisted code before production use, even for internal tooling
- Used Omnissa DEM to deploy PowerShell scripts for pre-login configuration, registry injections, and cache resets
- Migrated 200,000+ building files to SharePoint using Microsoft's migration agent on a dedicated sync VM, then built a Python script to generate anonymous share links so the Benchmarking team could distribute the right links to each building client
  - Python + Microsoft Graph API

### Security

- Used Darktrace to monitor and triage security incidents; tuned behavioral parameters to reduce false positives while keeping effective threat detection in place
- Maintained endpoint security through Omnissa Horizon instant clone deployment, Microsoft Defender, and a third-party security agent for malware detection
- Re-enrolled BYOD endpoints from mergers and acquisitions into Intune and deployed ScreenConnect for fast remote admin access

### Linux Servers

- Set up and actively maintaining GitLab server instance to host internally developed code; upgraded instance to v19.0.1-ee to enable API protocol support for internal tooling integrations
- Set up and configured WSL for Claude Code AI-assisted tooling for internal application development

### Updates/Adoption/Migration

- Redeployed VDI instant clone pools from Windows 10 to Windows 11 ahead of end-of-support deadline; improved desktop stability for end users as a byproduct of the clean image rebuild
- Led platform consolidation from RingCentral (IP phone) and Teams (messaging/video) to Zoom, improving VDI compatibility and reducing application management and configuration overhead
- Supported M&A integration: onboarded acquired company's users, data, and hardware within 1–2 months with limited visibility into their existing IT infrastructure and scope

### Documentation & Knowledge Management

- Reorganized IT documentation library on file server and SharePoint; standardized prefix naming conventions for cross-platform consistency
- Wrote Ajera Cloud login and usage guide; published to SharePoint IT document library and file server employee resource center
- Maintained runbooks and internal documentation for automation scripts, VDI image builds, and recurring IT procedures

### Disaster Recovery and Prep

- Assisted the IT Director in rebuilding our VDI after a catastrophic failure of a major datastore appliance that housed our VDI along with other auxiliary servers
- Installed and serviced server grade UPS appliances
- Did regular backup of critical server and VDI VM's onto HDD's stored in a secondary location along with cloud backups of Structural and Sustainability projects on redundant fileservers and Wasabi cloud storage

### Notable Help Desk Tickets

Selected tickets that show diagnostic depth, cross-system knowledge, or non-obvious resolutions. Pulled from the VCA IT support queue.

- **VDI freeze on Teams/Zoom call exit** — users' VMs locked up when ending video calls; monitored recurrence, identified resource spike pattern in instant clone pool, confirmed resolved after DEM and FSLogix tuning
- **Horizon Client 200% scaling on remote CAD desktop** — Luis's standalone Win11 machine had 200% system display scale set as default; Horizon Client inherited it for the remote session; resolved by correcting display scale on the physical machine
- **Inbound Zoom Phone queue — callers couldn't hear agents** — primary call queue routed to backup, answered calls had no audio on either side; investigated call queue routing config and Zoom Phone settings; resolved routing misconfiguration
- **AutoCAD 2020 PC3 print driver prompt** — Kris got a "Update PC3 File with New Printer" error on print; resolved by resetting DWG To PDF.pc3 via clearing `%APPDATA%\Autodesk\AutoCAD 2020` config files
- **Black screen + loading cursor after deferred security update** — Robyn postponed a NUMA Networks update prompt for ~1 week; on forced reboot, machine booted to black screen with spinning cursor; resolved by entering Safe Mode, logging in with local admin, completing the update cleanly
- **PyRevit not loading in Revit 2022** — Revit add-in failing to initialize for Thanh Nguyen; root cause was stale DEM profile cache for the Revit 2022 path; cleared via DEM console, add-in loaded correctly on next login
- **Scopbox Sync not appearing in Revit 2025** — plug-in was installed in the VDI gold image per VM_Matrix but not showing in Revit 2025; identified that the bundle was in the wrong Addins path; copied to `%ProgramData%\Autodesk\Revit\Addins\[RevitVersion]` for all Revit versions, confirmed fix on snapshot rebuild
- **Bluebeam licensing not applying post-outage** — Samir's Bluebeam license was not being applied after a Bluebeam service outage; re-sign-in resolved license application; also logged into Bluebeam Studio with the eplans shared account
- **10ZiG thin client config reset** — sporadic occurrences of 10ZiG configs wiping completely, sending users into an unexpected login flow; identified affected units, re-applied configuration through 10ZiG Manager, documented recovery steps
- **LastPass login recovery** — Gabe couldn't log in to LastPass; account was registered to a secondary email variant; found his password saved in Edge's built-in password manager; confirmed login, coached on password manager hygiene and potential conflicts between LastPass and Edge
- **Local Outlook (classic) not launching** — Angie's Outlook desktop app failed to open on her physical laptop (non-VDI); diagnosed and resolved via repair/re-registration of the Office installation
- **Omnissa Horizon Client lag for remote user (Mia)** — significant pointer lag when Mia connected remotely via Horizon Client 8.16.2; investigated connection speed and VDI session metrics; confirmed resolved after UAG and session routing tuning, no further reports

---

## iKrusher — IT Systems Administrator

_Feb 2024 – May 2024_

### Networking

- Administered and troubleshoot Ubiquiti networking hardware

### Microsoft 365

- Administered Microsoft 365 tenant for 56 users: Exchange Online, SharePoint, Teams, and licensing
- Implemented M365 policies and governance <!-- MISSING: which policies specifically? DLP, retention, shared mailbox governance? -->
- Onboarded users to M365 and wrote documentation and runbooks that cut future onboarding time by 30 minutes

### Endpoint Management

- Managed 50+ endpoints (Windows/macOS) in Intune with baseline configuration policies
- Standardized device build process with a documented baseline configuration <!-- MISSING: time saved per device? -->

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
- Onboarded new staff, ran training sessions, and covered day-to-day troubleshooting

### Identity & Access

- Managed Active Directory accounts and handled application access requests via the IT service desk

### Infrastructure & Security

- Set up and maintained secure remote access; kept endpoint security controls applied and current
- Rolled out BitLocker across 150+ Windows machines with IT leads in 2 business days, staggering mobile and stationary PCs to minimize downtime
