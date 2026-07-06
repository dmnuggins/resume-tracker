# Application Strategy: Network Administrator at Whittier College

**Generated:** Jul 2026
**Target Role:** Network Administrator
**Company:** Whittier College
**Application Status:** Not yet submitted
**Application #:** Third attempt (prior applications: ~2023 and ~2024–2025)

---

## Strategic Overview

**Opportunity Assessment:**
This is a persistent, deliberate pursuit. Dylan has cleared CV screening twice and made it to interview both times, which means the college has seen something worth exploring. The primary barrier has been Cisco/routing protocol depth at interview, not application screening. The CCNA (expected August 2026) is the most material change since the last application and should be the leading differentiator.

**Competitive Position:** Stretch candidate with improving position. Adjacent networking experience is genuine and growing; Cisco/routing protocol depth is still theoretical (CCNA curriculum), not operational. The third application signals commitment that most candidates don't demonstrate.

**Success Probability:** Moderate. The CCNA completion before or during the hiring process is the primary variable. If interviews happen post-August, the dynamic changes meaningfully. If interviews happen in July, honest framing of CCNA progress (with a date) is still more credible than the prior two attempts where the gap was simply open.

---

## Phase 1: Pre-Application (Now)

### Timeline
**Submit as soon as possible** — position is "until filled," no stated deadline. The hiring urgency may be real.

### Critical Tasks

#### Immediate
- [ ] Finalize cv-optimised.md — confirm CCNA completion date is still August 2026
- [ ] **Answer one open question before submitting:** Have you done any Cisco IOS configuration in a home lab environment (Packet Tracer, GNS3, EVE-NG)? If yes, add a brief Projects entry to the CV. If no, do not add it.
- [ ] Humanize and finalize cover-letter.md
- [ ] Export CV to PDF (pandoc HTML + Chrome headless, consistent with prior exports)

#### Before Submission
- [ ] **Consider submitting directly to Rudy Jordan** (whittierjobs@whittier.edu) rather than through a portal — you have a named contact and a prior relationship. A direct email with cover letter and CV attached is appropriate.
- [ ] Start or refresh Cisco Packet Tracer home lab practice — even 2–3 sessions on basic IOS commands (interface config, VLAN trunking, OSPF neighbors) will materially improve interview confidence if asked to demonstrate or discuss configuration

#### Submission
- [ ] Email to: whittierjobs@whittier.edu
- [ ] Subject line: Application — Network Administrator, [Your Name]
- [ ] Attach CV (PDF) and cover letter (PDF or inline)
- [ ] Save sent email for reference

---

## Phase 2: Post-Application

### Follow-Up Timeline

**Day 1:** Save confirmation; note date submitted

**Day 7:** If no response, send a brief follow-up directly to Rudy Jordan. Template:

> Subject: Network Administrator — Follow-Up, Dylan Nguyen
>
> Rudy,
>
> Just following up on my application for the Network Administrator role submitted [date]. Happy to answer any questions or provide additional context. Looking forward to hearing from you.
>
> Dylan Nguyen | (626) 559-7499

**Day 14:** Decision point — if still no response, one more brief check-in or move to background.

---

## Phase 3: Interview Preparation

This is the most critical phase given the two prior failures. The interview questions have escalated across attempts. Prepare specifically for the following:

### Networking Fundamentals (Round 1 pattern)
- OSI model layer by layer — know what happens at each layer and which protocols live there
- TCP vs. UDP — when each is used, why, handshake process
- ARP — how it works, when you'd see ARP issues, how to troubleshoot
- DNS resolution process end to end
- DHCP DORA process (Discover, Offer, Request, Acknowledge)
- Subnetting — be able to calculate subnets, host ranges, broadcast addresses quickly
- VLANs — what they do, how 802.1Q tagging works, access vs. trunk ports

### Cisco-Specific (Round 2 pattern, will likely continue)
- Cisco IOS command syntax — even if you haven't used it operationally, demonstrate fluency: `show ip route`, `show interfaces`, `show running-config`, `interface` commands, `ip address`, `no shutdown`
- OSPF — what it is, neighbor adjacency, areas, designated router election. Expect: "What would you check if OSPF neighbors aren't forming?"
- EIGRP — Cisco proprietary, metric calculation (bandwidth + delay), feasible successor
- BGP — high-level: iBGP vs. eBGP, AS numbers, when a campus network would use it (typically for multi-ISP or upstream provider peering). Don't overclaim operational experience.
- Spanning Tree Protocol — what it prevents, port states, RSTP vs. STP, root bridge election
- Trunking — 802.1Q, native VLAN, allowed VLANs on a trunk
- HSRP/VRRP — first-hop redundancy, why a campus would use it

### Campus Network Scenarios
- "Walk me through how you would design a VLAN structure for a campus with separate networks for staff, students, IoT, and guest Wi-Fi" — think through the segmentation, inter-VLAN routing (Layer 3 switch or router-on-a-stick), ACLs between segments
- "The network is slow. Where do you start?" — structured troubleshooting from physical layer up: check interfaces, duplex/speed, check routing table, ping tests, traceroute, check for loops
- "How would you approach documenting the existing network when you start?" — SNMP polling, CDP/LLDP neighbor discovery, draw topology, verify IP addressing scheme

### Your Honest Framing for Cisco Gaps
When asked about Cisco IOS or routing protocol experience:
> "My hands-on Cisco IOS exposure has been primarily through CCNA lab work — I'm completing the certification in August. At VCA we run Fortinet and HP Aruba, so I've built operational instincts on those platforms. The underlying concepts translate, and I'm actively building the Cisco command-line fluency to go with them."

This is more credible than vague confidence and more honest than claiming experience you don't have.

---

## Stakeholder Mapping

### Primary Decision-Maker
**Name:** Rudy Jordan
**Title:** Assistant Director of Systems and Networking
**Context:** Has interviewed Dylan twice. Knows him. The relationship is an asset — this is not a cold application.
**Engagement Strategy:** Submit directly to Rudy via email (not just HR portal). The personal cover letter is addressed to him. No need to connect on LinkedIn separately — the direct email is the right channel here.

---

## Risk Assessment

### Risk 1: Still lacks Cisco IOS operational experience
**Likelihood:** High (it will come up again)
**Impact:** High
**Mitigation:** CCNA in progress with specific completion date; home lab practice before interview; honest framing at interview (see above)
**Proactive Messaging:** Address directly in cover letter. Do not wait for them to raise it.

### Risk 2: Third application raises a "ceiling" concern
**Likelihood:** Medium
**Impact:** Medium
**Mitigation:** Cover letter frames this as determination + material new credential, not just repetition. The CCNA is the answer to the question "what's different this time."
**Proactive Messaging:** "Third time pursuing this role, each time with a clearer sense of what it takes."

### Risk 3: CCNA not completed before offer
**Likelihood:** Medium (August 2026 target; hiring timeline unknown)
**Impact:** Medium
**Mitigation:** Be specific about the date. "Expected August 2026" is a credible commitment if you're actively studying.

### Competitive Advantages to Emphasize

1. **Prior relationship with the hiring manager**
   - You are not a cold candidate. Two prior interviews means Rudy knows your communication style, how you present, and that you follow through. Lean into this.
   - Relevant at: Interview

2. **Fortinet firewall administration with specific use cases**
   - The inventory documents named scenarios (VLAN isolation, guest network segmentation, IoT port management). Most candidates say "managed firewall." You can say specifically what you configured and why.
   - Relevant at: CV, interview

3. **CCNA in progress with a concrete date**
   - The prior two applications did not have this. This is the primary differentiator.
   - Relevant at: Cover letter, profile, certifications, interview

4. **Active pursuit across three applications over multiple years**
   - Signals genuine motivation for this specific type of role, not spray-and-pray job searching.
   - Relevant at: Cover letter, interview ("why do you keep applying here?")

---

## Decision Framework

### Must-Haves
- Role is genuinely networking-focused, not sysadmin with networking duties
- Compensation at or above $81,368 (the listed salary)
- Single network admin / owner model (not junior support under another network engineer)

### Important
- Management of Cisco infrastructure (this is the learning opportunity you're pursuing the CCNA for)
- Stability — small college IT teams tend to have low turnover if the fit is right

### Red Flags to Watch For
- If asked about the prior admin's departure — probe gently for whether this is a recurring vacancy due to environment vs. role evolution
- If the team headcount is very small and on-call expectations are more than occasional — clarify scope before accepting

---

## If Rejected Again

- Ask Rudy directly for honest feedback on what the gap is. You've earned that conversation by applying three times.
- Use the feedback to determine whether this is a "keep trying after CCNA completes" situation or whether the fit expectation is too far from your current trajectory.
- Continue CCNA regardless — the credential opens adjacent roles even if Whittier doesn't work out.

---

## Application Tracking

| Metric | Target | Actual |
|---|---|---|
| Submission date | ASAP | |
| Follow-up sent | Day 7 post-submission | |
| Response received | | |
| Interview date | | |
| Offer / rejection | | |

---

*Generated using Career Helper skill by Paul Bratcher ([LinkedIn](https://www.linkedin.com/in/paul-bratcher/) | [GitHub](https://github.com/Zal4DW/career-helper)). Found this helpful? Share your success story or suggest improvements on GitHub!*
