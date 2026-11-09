# Application Strategy: Network Administrator at Montebello Unified School District

**Generated:** Oct 2026
**Target Role:** Network Administrator (Information Systems)
**Company:** Montebello Unified School District
**Job Number:** 26-10-NA-RS
**Salary:** $89,928.84 to $118,224.96/yr
**Closes:** Tuesday, Nov 4, 2026, 4:00 PM PT
**Application Status:** Not yet submitted

---

## Strategic Overview

**Opportunity Assessment:**
This posting lines up closely with the network work you do now: LAN/WAN across multiple sites, firewall security, voice network oversight, ISP and vendor coordination, servers, and documentation. It is an open competitive recruitment that fills an eligibility list valid for six months, so one pass through the exam process can lead to more than one vacancy. The pay range is the highest of any network role you have tracked.

**Competitive Position:**
Moderate. You are strong on day-to-day duties and you meet the degree requirement outright. The weak spots are the experience count in the minimum qualifications, routing protocols, SNMP-based network management, and the legacy WAN protocols in the posting. You also have no school district experience, which is preferred but not required.

**Success Probability:**
Moderate, with the minimum qualifications screen as the first and biggest hurdle (see Risk 1). If you pass that screen, the exam stages (written, performance, oral) reward exactly the kind of study you did for Whittier.

---

## Minimum Qualifications Check

| Requirement | Status | Notes |
| --- | --- | --- |
| Bachelor's in computer science, math, or related field | Met | BS Computer Science, Cal Poly Pomona |
| 4 years of professional experience designing, installing, modifying, and maintaining network infrastructure | At risk | See Risk 1 |
| Valid CA driver's license, auto insurance, personal vehicle | Confirm | Mileage is reimbursed |
| MCSE (highly preferred) | Not held | Microsoft retired the MCSE; few applicants will have a current one |
| School district experience (highly preferred) | Not held | Use the "why a district" angle in the oral |

---

## Phase 1: Pre-Application (Now to Nov 4)

### Timeline

**Target Submission Date:** Monday, Nov 3 (one day of buffer before the 4:00 PM Nov 4 close)
**Days to Prepare:** 5

### Critical Tasks

#### Immediate

- [ ] **Paste the Questions tab from the posting.** The exam may include a scored supplemental questionnaire, and that is often the first scored stage. Those answers matter more than the resume.
- [x] Confirm CCNA status (still in progress as of Nov 2)
- [x] SNMP experience confirmed and added (see Risk 3)
- [x] Q05 decided: answer No (about 3 years of network experience confirmed Nov 2; the requirement is 4)
- [ ] Decide whether to submit anyway (see Risk 1)
- [ ] Add supervisor names and contact info to Q15
- [ ] Confirm you have proof of degree available to upload if the portal asks for it.

#### Before Submission

- [ ] Fill in the full application work history. The posting says an incomplete application means disqualification, and "see resume" usually counts as incomplete.
- [ ] In each job entry, write out the network duties explicitly so the analyst can count qualifying time (see Risk 1).
- [ ] Attach the PDF CV.
- [ ] Optional: a short cover letter. It is not required. If you write one, reuse the Whittier structure and add one line on why you want to work for a district.

#### Submission Checklist

- [ ] Full application complete, with every job entry filled in
- [ ] Supplemental questions answered
- [ ] CV attached
- [ ] Confirmation saved; tracker updated
- [ ] Git tag: `application/montebello-network-administrator-2026-11-03`

---

## Risk Assessment and Mitigation

### Risk 1: The 4-year network infrastructure experience requirement

**Status (Nov 2):** Confirmed at about 3 years. The requirement isn't met, and Q05 will be answered No. Submitting anyway costs an hour or two, puts your materials in front of MUSD Information Systems, and the analyst might still credit your broader IT time. But expect to be screened out. Either way, watch for a Senior Network Technician posting at MUSD.

**Likelihood:** High
**Impact:** High (screened out before any exam)

Your time by role:

| Role | Dates | Duration | Network infrastructure content |
| --- | --- | --- | --- |
| VCA Consultants | May 2024 to present | about 2 yr 6 mo | Strong: three-site LAN/WAN, FortiGate, VLANs, DMZ, DHCP, voice |
| iKrusher | Feb to May 2024 | 3 mo | Moderate: Ubiquiti, ISP coordination |
| The Flex Company | Nov 2020 to Jul 2022 | 1 yr 8 mo | Light: NAS/cloud backup, access management |
| Five Acres | Jul 2017 to Jul 2019 | 2 yr | Light to moderate: secure remote access (IT Tech role only) |

You have about 6.4 years of total IT experience. A strict count of network-heavy work comes to about 2.75 years. Classified personnel commissions often credit roles where network work was a regular, significant part of the job, but a strict reviewer could screen you out.

**Mitigation:**
- In the application work history, list every network task you actually did in each role: remote access, connectivity troubleshooting, ISP coordination, Ubiquiti and switch work. Do not inflate anything. Just make sure real network work isn't buried under help desk language.
- If you are unsure, email the Personnel Commission before Nov 4 and ask how they count partial network duties. It is a legitimate question and it costs nothing.
- Apply anyway. The cost is a few hours, and a rejection at the qualifications stage gives you useful information for future district postings.

**Proactive messaging (oral appraisal, if asked):**
"Most of my network infrastructure work has been at VCA over the last two and a half years, where I'm responsible for the firewall, switching, VLANs, and DHCP across three sites. Before that, the network side was part of broader IT roles: remote access, ISP coordination, and connectivity troubleshooting."

### Risk 2: Routing protocols (OSPF, BGP, RIP) and legacy WAN technologies (frame relay, ISDN, BRI, PRI, HDLC)

**Likelihood:** High that these come up on the written exam
**Impact:** Medium

This is the same gap that showed up at Whittier. The protocol list reads like it was carried over from an older class specification, so the written exam may include basic definitions.

**Mitigation:**
- Reuse the Whittier interview prep and subnetting exercises. OSPF, BGP, DHCP, DNS, and the OSI model are already written up there.
- Add one page of legacy WAN definitions to know cold: frame relay (DLCI, PVC), ISDN BRI (2B+D) vs. PRI (23B+D in North America), HDLC (Cisco default on serial links), and DSU/CSU. PRI is still relevant for voice, since many district phone systems connected to the carrier over PRI trunks.
- Also cover NTP, SMTP, FTP, and RIP basics: ports, purpose, and one troubleshooting example each.

### Risk 3: SNMP and automated network management

**Likelihood:** Medium
**Impact:** Low to Medium (partly closed)

The posting calls out an SNMP-based network management system. You've confirmed SNMP monitoring for the ESXi servers at VCA, plus SNMP monitoring of UniFi gear in your homelab. Both are now in the career inventory and the CV. The remaining gap is scale: you haven't run a network management system across many sites.

**Oral prep:** know SNMP v2c vs. v3 (community strings vs. authentication and encryption), polling (UDP 161) vs. traps (UDP 162), what a MIB and an OID are, and which tool and metrics you used for the ESXi monitoring.

### Risk 4: No school district experience

**Likelihood:** High (it's a fact)
**Impact:** Low to Medium (preferred, not required)

**Mitigation:** In the oral, connect your multi-site experience to running a district with many sites, and your Five Acres time to working in a mission-driven, compliance-heavy organization. Explain in your own words why you want to work in public education. Don't borrow a reason.

### Competitive Advantages to Emphasize

1. **Current, hands-on firewall ownership**
   - Evidence: FortiGate 200F on FortiOS 7.4.12; firmware upgrades, policy cleanup, log review, and VLAN/guest/IoT segmentation
   - When: written work history, supplemental questions, oral

2. **Voice network troubleshooting**
   - Evidence: the LLDP phone provisioning fix, the Zoom Phone call queue fix, and the RingCentral-to-Zoom migration
   - When: oral (it maps directly to the duty "oversee the daily operations of the voice network")

3. **Change discipline and documentation**
   - Evidence: the Denver firewall rollback, made possible by documenting changes as you went
   - When: oral (a strong STAR story for "maintain security of network" and "documentation")

4. **Programming background**
   - Evidence: BS Computer Science, plus PowerShell, Python, and Graph API automation
   - When: written exam and oral (the posting asks for structured programming, which most network candidates lack)

---

## Phase 2: Post-Application

Civil service timelines are slow. Expect several weeks between the close date and any exam notice.

- **Submission day:** save the confirmation and update `applications.md`
- **Within 2 weeks after close:** watch email and the portal for a notice on minimum qualifications or the exam schedule
- **If screened out:** ask the Personnel Commission which requirement wasn't met. That answer tells you how they count network experience for future postings.

---

## Phase 3: Exam and Interview Preparation

The posting lists possible stages: scored supplemental questionnaire, written exam, performance exam, oral appraisal interview, and others.

- **Written exam:** protocol definitions (the full list above), subnetting, OSI model, troubleshooting order, and basic programming concepts
- **Performance exam:** possibly hands-on config or troubleshooting. Run through Packet Tracer basics: VLANs, trunking, inter-VLAN routing, DHCP helper-address, an OSPF neighbor, and an ACL.
- **Oral appraisal:** reuse the Whittier STAR stories (LLDP, Denver rollback, UAG bottleneck, conflict story), and add one FortiGate firmware upgrade story covering prep, backout plan, and verification.
- Review `feedback_network_admin_interview_gaps`: hardware and firmware versions (now in the inventory: FortiGate 200F, FortiOS 7.4.12 build 2902), DHCP methodology, and VPN beyond SD-WAN.

---

## Decision Framework

### Must-Haves
- Pay within the posted range (the bottom step, $89,929, is already above Whittier's $81,368)
- Reasonable commute to Montebello from Rosemead (short, which is a plus)

### Questions to Ask at the Oral
- What does the current WAN between school sites look like (dark fiber, carrier Ethernet, SD-WAN)?
- What phone system does the district run, and who is the maintenance vendor?
- What network management or monitoring platform is in place?
- How is the network team structured relative to Senior Network Technicians?

---

## Notes and Observations

- The posting distinguishes this role from Senior Network Technician. If Montebello Unified posts that class, it is a natural fallback with a lower experience bar.
- The eligibility list lasts six months. A good rank can produce an offer later even if the first vacancy goes to someone else.

---

*Generated using Career Helper skill by Paul Bratcher ([LinkedIn](https://www.linkedin.com/in/paul-bratcher/) | [GitHub](https://github.com/Zal4DW/career-helper)). Found this helpful? Share your success story or suggest improvements on GitHub!*
