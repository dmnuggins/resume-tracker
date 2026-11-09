# Supplementary Questions: Montebello Unified School District

## Network Administrator (Job #26-10-NA-RS)

The instructions warn that answers will be "further evaluated in upcoming test parts" and that exaggeration can mean disqualification and a bar from future MUSD jobs. Every rating below is one you should be able to back up with a specific example in the oral interview. The evidence notes are for you, not for the form.

---

## Q01: Acknowledgment

Dylan Nguyen

---

## Q02: Bachelor's degree in computer science, mathematics, or related field

Selected answer: Yes

Attach: diploma or a transcript that shows the graduation or conferral date (Cal Poly Pomona, BS Computer Science). A transcript without a date will be rejected.

---

## Q03: Valid driver's license

Selected answer: Yes

Attach: scan of the front of your license.

---

## Q04: Automobile liability insurance

Selected answer: Yes

Attach: current insurance card or declarations page.

---

## Q05: Four years of professional experience designing, installing, modifying, and maintaining network infrastructure

Selected answer: No

**Note:** You confirmed about 3 years of network infrastructure experience (Nov 2, 2026), which is short of the required 4. Answering No probably means you'll be screened out at the minimum qualifications stage. It also keeps your record with MUSD clean and matches what Q15 shows. Q15 still gets a full answer, not "N/A," because you do have related experience; it just falls short of four years. Your time by role, for reference:

| Role | Dates | Hours/wk | Network infrastructure share |
| --- | --- | --- | --- |
| VCA Consultants, IT Technician II | May 2024 to present (about 2 yr 6 mo) | 40 | Core of the role |
| iKrusher, IT Systems Administrator | Feb 2024 to May 2024 (3 mo) | 30 | Part of the role |
| Five Acres, IT Technician | Jul 2017 to Apr 2018 (9 mo) | 40 | Small part (secure remote access) |
| The Flex Company, IT & Ops Coordinator | Nov 2020 to Jul 2022 (1 yr 8 mo) | 40 | Small part (local NAS) |

Network-focused time is about 2.5 years, or about 3.5 years if you count every role with any network work. Neither reaches 4 years unless MUSD credits general IT roles that include network duties. Q15 will show these dates either way, so answering Yes when Q15 adds up to less than 4 years is the kind of mismatch the warning describes.

You no longer need to ask the Personnel Commission how they count experience; even a generous count doesn't reach 4 years. If you're screened out, you'll be in good standing for a future Senior Network Technician posting, or for this class once you reach 4 years of network work (about late 2027 at your current pace).

---

## Q06: Microsoft Certified Systems Engineer (MCSE)

Selected answer: No

---

## Q07: Analyzing, designing, coding, and implementing software for network equipment (routers, switches, servers, workstations, modems, DSUs)

Selected answer: I have done this as a regular part of my job duties.

Evidence: FortiGate 200F policies and firmware upgrades, HP Aruba switch configuration (VLANs, ports, LLDP), ESXi host and virtual NIC setup, DHCP configuration, the DMZ connection server, and Windows and Linux server builds. Expect a follow-up on the "coding" part: PowerShell and Python automation, plus the GitLab server.

---

## Q08: Administering network services, capabilities, and privileges at the user, workstation, sub-network, server, and network levels

Selected answer: I have done this as a regular part of my job duties.

Evidence: Active Directory and Entra ID for 120+ accounts (user level), Group Policy by OU and Intune (workstation level), VLANs, guest network, and DHCP scopes (sub-network level), ESXi, Windows Server, and GitLab (server level), and firewall policies across three sites (network level).

---

## Q09: Maintaining the security of a network for an organization

Selected answer: I have done this as a regular part of my job duties.

Evidence: FortiGate firmware upgrades, policy cleanup, and log review; Darktrace monitoring and tuning; Duo MFA and Conditional Access; LAPS; Defender; guest and IoT segmentation. "Extensively and at a high level of complexity" would be hard to defend for a three-site, 120-user organization.

---

## Q10: Automated network management system using SNMP and graphical network management software

Selected answer: I have done this independently, but only occasionally.

Evidence: you set up SNMP monitoring for the ESXi servers at VCA, and you run SNMP monitoring on UniFi equipment in your homelab. That supports "independently," but it isn't a district-wide network management system you run every day, so "occasionally" is the honest level. Be ready to name the monitoring software, what you polled (CPU, memory, interface traffic, traps), and which SNMP version you used. Bring up the homelab only in the oral; this question is about work experience.

---

## Q11: Consulting with users to determine network requirements, identify problems, and determine feasibility of network projects

Selected answer: I have done this as a regular part of my job duties.

Evidence: department requests that turned into firewall and VLAN work (air quality dashboard, USPS postage machine, isolated development host, IoT devices), vetting applications with department leads before integration, remote access requirements for distributed staff, and the RingCentral-to-Zoom consolidation.

---

## Q12: Operating computers and peripherals, including terminals, mass storage and backup devices, servers, workstations, printers, and scanners

Selected answer: I have regular experience performing this job duty.

Evidence: thin client terminals (10ZiG), TrueNAS storage, offsite HDD and Wasabi backups, the Flex NAS with S3 and Glacier, ESXi hosts, UPS units, 100+ endpoints, and printer support.

---

## Q13: Overseeing daily operations of the voice network, including oversight of telecommunications work

Selected answer: I have done this as a regular part of my job duties.

Evidence: Zoom Phone administration after you led the RingCentral-to-Zoom migration, call queue routing fixes, IP phone provisioning and the LLDP fix. Drop this to "independently, but only occasionally" if voice work is rare in a normal month at VCA. You have no history overseeing a telecom vendor's technicians, so be ready to say that in the oral.

---

## Q14: Troubleshooting hardware, software, and network problems and assisting in resolution

Selected answer: I have done this extensively and at a high level of complexity.

Evidence: troubleshooting has been the core of every role since 2017. Complex cases include the UAG bottleneck, the LLDP provisioning failure, the Denver site-to-site rollback, the vGPU driver failure fixed over ESXi SSH, DEM profile corruption, and the Zoom Phone no-audio routing problem. If that feels like a stretch, "regular part of my job duties" is the safe choice.

---

## Q15: Describe your four years of network infrastructure experience, including supervisor names and contact information

**Fill in before submitting:** supervisor names, titles, and phone or email for each role. Mark any you don't want contacted.

VCA Consultants, IT Technician II, May 2024 to present, 40 hours per week
Supervisor: [MISSING: name, IT Director, phone/email]

I maintain the network for our three offices in Orange, Los Angeles, and Denver. The equipment is HP Aruba switches, routers, a FortiGate 200F firewall on FortiOS 7.4.12, Dell EMC ESXi hosts, and TrueNAS storage. I handle the FortiGate's firmware upgrades, and I go through its logs and clean out old or duplicate policies.

Most of my firewall work starts as a department request. Someone needs a device or service reachable, and I write the policies and VLAN assignments to make it work. Recent ones include an air quality management dashboard, a USPS postage machine, a development machine isolated on our guest network, and desktop and IoT devices that needed their own VLANs and switch ports. I also set up a DMZ connection server so thin clients outside our network could reach our internal management server without exposing it.

On the server side, I set up DHCP scopes and IP reservations in Active Directory for new virtual servers, configure virtual NICs on the ESXi hosts, and set up SNMP monitoring for those hosts. I helped with our core switch upgrades and the DAC rewiring that went with them.

For voice, I led our move from RingCentral IP phones to Zoom. When phones on our third floor wouldn't provision, I tracked the problem to LLDP being turned off on the access switch and fixed it.

Remote staff connect through VMware Horizon with Duo MFA, which I set up and maintain. When remote users started lagging, I found the bottleneck in our Unified Access Gateway.

I write down changes as I make them. That paid off when a new firewall rule cut off our Denver servers: I had the details in front of me and rolled it back within minutes.

iKrusher, IT Systems Administrator, February 2024 to May 2024, 30 hours per week
Supervisor: [MISSING: name, title, phone/email]

I administered and troubleshot the company's Ubiquiti network hardware and was the main contact for our internet service providers and vendors, owning connectivity tickets and escalations through resolution.

The Flex Company, IT and Operations Coordinator, November 2020 to July 2022, 40 hours per week
Supervisor: [MISSING: name, VP of Business Operations or Head of Business, phone/email]

I built and maintained a local network attached storage system for our creative assets, backed up to Amazon S3 and Glacier, and supported staff connecting to company systems from the office and from home.

Five Acres, IT Technician, July 2017 to April 2018, 40 hours per week
Supervisor: [MISSING: name, title, phone/email]

I set up and maintained secure remote access for staff and kept endpoint security controls current in a healthcare environment with strict compliance requirements, including a BitLocker rollout across more than 150 Windows machines.

---

## Q16: All required documents attached

Selected answer: Yes (only after the degree, license, and insurance are actually attached)

---

## Q17: Affirmation

Dylan Nguyen

---

_MUSD Network Administrator Application | Job #26-10-NA-RS | Closes 11/4/2026 4:00 PM PT_
