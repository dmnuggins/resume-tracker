# Supplementary Questions: South Coast AQMD

## Information Technology Specialist I (Job #26:25:EV)

---

## Q02: Years of experience

Selected answer: I have four (4) years or more of related experience.

---

## Q03: Describe your experience

_From your response to Question #2, please describe your experience, including organization(s), job title(s), specific duties, and duration (dates)._

VCA Consultants | IT Technician II | May 2024 - Present

I cover infrastructure, networking, and user support across three offices (Orange, LA, Denver). That means managing LAN/WAN with HP Aruba switches, Dell EMC ESXi hosts, and TrueNAS storage; writing Fortinet firewall rules and VLAN assignments; keeping remote access running through Horizon View with Duo MFA; and running the Omnissa Horizon VDI environment for 120 concurrent users.

I also manage Windows endpoints in Intune for 100+ devices and AD/Entra ID accounts for 120+ users, monitor security events in Darktrace, and maintain a Linux server running GitLab for internally developed scripts. Earlier this year I helped rebuild the VDI after a primary datastore appliance failed and installed server-grade UPS hardware. I also led the platform consolidation from RingCentral and Teams to Zoom, and supported an M&A integration that onboarded an acquired company's users, data, and hardware within about two months.

iKrusher | IT Systems Administrator | Feb 2024 - May 2024

I administered Ubiquiti networking hardware, managed Microsoft 365 for 56 users (Exchange Online, SharePoint, Teams), and handled endpoint configuration across Windows and macOS in Intune. I was the main contact for vendor and ISP issues, taking tickets from intake to close.

The Flex Company | IT & Operations Coordinator | Nov 2020 - Jul 2022

I handled Tier 1-2 support for 20+ staff in a hybrid environment and managed user accounts across Google Workspace and other SaaS tools for 30+ people. I maintained a local NAS with S3 and Glacier offsite redundancy, migrated 10,000+ company files to Google Workspace Shared Drives, and documented backup and recovery procedures.

Five Acres | IT Technician | Jul 2017 - Apr 2018

I provided IT support in a regulated healthcare setting covering hardware, software, and business applications, managed Active Directory accounts through the service desk, and coordinated a BitLocker rollout across 150+ Windows machines in two business days.

---

## Q04: Knowledge and experience with data networks

_Describe your knowledge and experience setting up, configuring, maintaining, or troubleshooting data networks._

At VCA, I manage the network across three offices. Day to day that means Fortinet firewall rules and VLAN assignments for workstations and IoT devices. The needs vary: I've written rules for an air quality dashboard that needs to reach an external data source, a dev machine that stays isolated on its own guest network, and office equipment that needs specific ports open. When we brought in a new server, I configured virtual NICs on the Dell EMC ESXi hosts. I also helped with a core switch upgrade that required rewiring with DAC cables.

Remote access runs through Horizon View with Duo MFA. When users started getting session lag and disconnects, I traced the problem through the connection path and found a UAG bottleneck. That one took some time in the logs before the cause was clear. I also set up the 10ZiG thin client management server to reach devices outside the local network through a DMZ-hosted secure connection server, so off-site thin clients could be managed the same way as on-site ones.

At iKrusher, I administered Ubiquiti networking hardware and handled connectivity issues on-site.

Most of my networking knowledge comes from owning these environments directly, along with studying for the CCNA and running Ubiquiti hardware on my home network.

---

## Q05: Service requests, diagnosis, and troubleshooting

_Describe your knowledge and experience receiving and evaluating requests for service; diagnosing problems; troubleshooting and implementing remedial actions._

At Five Acres, I staffed the IT service desk in a healthcare environment where requests came in by phone, email, and walk-up. I triaged by urgency, worked with the requester to understand what was actually happening, then fixed it or escalated. Everything from hardware failures to account requests came through the desk.

At iKrusher, I was the main contact for vendor and ISP problems. When something went wrong, I owned it from intake to close: logged the issue, got on the phone with the vendor, and tracked it through to resolution.

At VCA, the diagnostic work gets more layered. When remote users started having session problems in Horizon, I worked through the connection path, checked client-side settings, connection server event logs, and UAG load, and traced the problem to a bottleneck at the gateway. For VDI issues like profile corruption or authentication failures, I go through Horizon event logs, DEM profile configurations, and Intune compliance status depending on what the symptoms suggest. That process brought help desk tickets for authentication and profile problems down from several per day to a few per week.

Not all problems stay at the OS layer. When a VMware ESXi host wouldn't take a vGPU driver update through the standard remediation interface, I SSHed into the host and unloaded the NVIDIA kernel module manually before rerunning the patch. When a user's laptop booted to a black screen after a long-deferred endpoint agent update, I got in through Safe Mode with a local admin credential, completed the blocked update, and returned the machine without data loss.

VDI application failures tend to look like app problems until you look at the environment. When a Revit add-in stopped loading, the problem wasn't in Revit: a stale DEM profile cache from a prior session was blocking it. Clearing the cache through the DEM console fixed it. A separate case involved a plugin that was installed in the gold image but not appearing in a specific Revit version. That was a path problem; the bundle was in the wrong Addins directory for that version, which only became clear once I looked at how Revit resolves add-in paths.

Sometimes a symptom points somewhere it doesn't belong. When a user's Horizon Client session was scaling everything to 200%, the remote connection was fine. The cause was a 200% display scale set on the physical machine, which the session was inheriting. Fixing it there cleared the issue.

---

## Q06: End user support and communication

_Describe your experience providing technical support to end users, including communicating technical information to non-technical staff, prioritizing workload, and ensuring customer satisfaction._

At VCA, most of my users are engineers and project managers. They don't want the technical walk-through. They want to know if it's fixed, when, and whether there's a workaround while they wait. When we moved the VDI from Windows 10 to Windows 11, I put together plain-language updates for each team lead: what to expect during the cutover, and what to do if something looked off after the switch.

At iKrusher, I wrote M365 onboarding runbooks plain enough that new hires could follow them without anyone walking them through it. That cut setup time by 30 minutes per account.

At Five Acres, I ran training sessions and handled day-to-day troubleshooting for staff who weren't technical. In healthcare, you can't leave people confused about an IT problem when they're working with clients. You have to get to the point and leave them with something they can act on.

For prioritizing: anything that stops someone from working goes to the front. When I'm juggling multiple issues, I check in with whoever's waiting so they're not left wondering.

---

_South Coast AQMD Application | Job #26:25:EV | Closes 6/19/2026_
