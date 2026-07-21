# Interview Preparation: Network Administrator at Whittier College

**Generated:** July 2026
**Target Role:** Network Administrator
**Company:** Whittier College
**Interview Stage:** Third application — Round 1
**Interviewer:** IT Network Systems Director (Whittier College)
**Context:** Third application. You have passed CV screening twice and reached the first-round interview both times but did not advance past it either time. Prior first-round interviews covered Cisco IOS knowledge and IT/network fundamentals. The CCNA in progress (expected August 2026) is your primary differentiator — it directly addresses the Cisco gap that likely caused you not to advance.

---

## Interview intelligence

**Expected format:** Structured conversation, likely 45–60 minutes in-person or video
**Likely interviewers:** IT Network Systems Director (Rudy's director or equivalent senior IT leader)
**Known interview structure (from prior first-round interviews):**

1. Introduction
2. What you've been up to since last time
3. Cisco IOS knowledge
4. IT and network fundamentals (campus design, outage troubleshooting, non-technical communication)

**Your three objectives:**

1. Land the CCNA as a concrete credential in progress, not a vague aspiration
2. Show that your VCA work has grown materially since last interview — specific stories, not just titles
3. Demonstrate that you think like an infrastructure owner, not just a break-fix technician

---

## Section 1: Introduction

### "Tell me about yourself" / "Walk me through your background"

**What they're assessing:** Whether you can give a coherent, confident narrative. They've reviewed your CV twice — this is about how you frame yourself and what's changed, not listing jobs.

**Your answer (2 minutes, spoken):**

> I've been continuing my work as a systems and network admin at VCA Consultants. Since I joined, our user base has grown and management scope has expanded to 2 office sites plus a large remote workforce. I've gotten more involved with the physical and virtual networking infrastructure — firewall rules, access switch configuration, VMware virtual switch config, VLAN management — alongside my usual IT responsibilities: administering our VDI, remote endpoints, user deployment, and VMware server infrastructure. I made an effort to be more involved and aware of the internal network, but my responsibilities are broad by design.
>
> The reason I keep coming back for this role is that I want to go deep on the network side specifically. At VCA I cover a lot of ground, but the breadth of the role means I can't specialize. I hear online and amongst my peers that no one really likes to deal with the network, but to me, I see it as an opportunity to push myself and take the path least treaded. That and an opportunity to take ownership of something that can both impact and empower hundreds of people (students, and faculty alike)
>
> Since we last spoke, the biggest change is my progress on the CCNA. I'm wrapping up coursework this month and sitting the exam in late August. I've been running Packet Tracer labs and applying what I'm learning, making the connections between the theoretical with the practical applications in our production infrastructure.

**Key points to hit:**

- Current scope (3 sites, specific hardware)
- Why this role specifically (don't make it sound like you're job hunting)
- CCNA as the material change — be specific about the August date

---

### "Why are you applying again? What's different this time?"

**What they're assessing:** Whether you've actually addressed the gap, or are just persistent without progress.

**Your answer:**

> Honestly, the honest answer from the last interview was that my Cisco IOS experience was superficial. Since picking up my studies for the CCNA I force myself to go beyond knowing the concepts and actually work with lab based and production side configurations. I've been practicing in Packet Tracer: OSPF neighbor setup, VLAN trunking, ACLs, interface configuration. And at VCA the network scope has grown, so I'm coming in with more production troubleshooting behind me than I had last time.

---

## Section 2: What you've been up to

These are the specific VCA stories you should be ready to tell in depth. Each one maps to a likely follow-up in later sections.

---

### Story A: IP phone LLDP rollout (troubleshooting + VLAN/VoIP)

**When to use:** "What have you been working on recently?" / any VoIP or VLAN troubleshooting question

**STAR:**

- **Situation:** Rolling out Poly Edge E500 IP phones across the local office on Zoom Phone. Deployment stalled — half the office phones wouldn't complete one-touch provisioning to the Zoom provisioning server.
- **Task:** Diagnose and resolve the issue without disrupting the rest of the office.
- **Action:** Worked with our IT Director to check the phone configs, port configs, and VLAN assignments first — those all checked out. Dug into the HP Aruba switch's configuration options next, working through the CLI with help from ChatGPT and Zoom's documentation for reference. Found that LLDP wasn't enabled on the switch, confirmed against HP Aruba's own documentation. Toggled LLDP on.
- **Result:** Phones immediately connected to the Zoom provisioning server and completed one-touch deployment. Root cause documented so LLDP is enabled by default on any new phone port configuration going forward.

**Key phrase:** "The protocols tell you exactly what should be happening — the diagnostic work is just matching what you're seeing to what the protocol says should be true."

---

### Story B: Fortinet rule documentation (change management + rollback)

**When to use:** "Tell me about a time something went wrong" / documentation / change management questions

**STAR:**

- **Situation:** Mid-change on the Fortinet firewall — adding a new rule to enable a department service. Site-to-site connectivity to the Denver office dropped.
- **Task:** Restore service as fast as possible, understand what happened.
- **Action:** Because I document changes as I go — what the rule is, what it's supposed to do, what the before state was — I had the context immediately. Reverted the new rule. Denver connectivity restored within minutes. Then reviewed what the interaction was between the new rule and the existing policies, fixed the ordering, tested again.
- **Result:** Total outage was under 5 minutes. No ticket needed from Denver — I reached out to confirm restoration before they noticed.

**Key phrase:** "A configuration mistake is recoverable. A configuration mistake with no documentation is a crisis."

---

### Story C: UAG bottleneck diagnosis (systematic troubleshooting)

**When to use:** "How do you troubleshoot a network issue?" / performance diagnosis questions

**STAR:**

- **Situation:** Remote staff started reporting session latency on VMware Horizon VDI. Not all users, not consistent.
- **Task:** Identify whether this was a client-side, network, or server-side issue.
- **Action:** Started at the edge — checked whether latency correlated with specific users, times, or sites. Didn't. Traced the connection path from external client through the UAG (Unified Access Gateway) into the internal Horizon infrastructure. Compared client-side latency logs against UAG session throughput metrics. Found the UAG was hitting CPU saturation under concurrent session load. Recommended and implemented a resource increase on the UAG VM; monitored for recurrence.
- **Result:** Latency complaints stopped. Added UAG CPU utilization to the monitoring dashboard.

**Key phrase:** "I followed the connection path methodically. The UAG is the chokepoint between outside and inside, so that's where I looked once client-side and server-side checked out."

---

### Story D: DMZ connector server (security architecture)

**When to use:** "Tell me about a security or network design decision you made"

**STAR:**

- **Situation:** External devices needed to reach the internal management network for administration — but opening the perimeter directly was not acceptable.
- **Task:** Enable the access without creating a firewall hole into the internal network.
- **Action:** Configured a secure connector server in the DMZ. External devices connect to the DMZ host; the DMZ host has a restricted, encrypted connection to the internal management VLAN. Nothing from outside reaches the internal network directly.
- **Result:** External administration capability without perimeter exposure. Firewall policy documented with the rationale for the DMZ architecture.

---

### Story E: Access token conflict during acquisition scoping (interpersonal conflict, cross-team communication)

**When to use:** "Tell me about a conflict with a coworker" / "Tell me about a time you disagreed with someone" / any interpersonal or cross-team communication question

**STAR:**

- **Situation:** VCA was scoping a potential migration of a recently acquired company's production repos to a self-hosted Git instance, for better long-term management. It was exploratory only — no migration had been approved.
- **Task:** Assess feasibility without disrupting the acquired company's existing deployment pipeline or overstepping into systems that weren't mine yet.
- **Action:** I requested an access token from their team so I could look at repo structure. To me it was routine, low-stakes exploratory access. From their side, an outside admin requesting elevated access to their production repos looked like an attempt to take over and put their deployments at risk — a reasonable read if you don't have the context I had. It escalated to the point that the conversation got moved up to both of our respective managers, who clarified intent and scope, and things were smoothed over from there.
- **Result:** Scoping continued collaboratively. More importantly, I walked away with a concrete lesson about how I initiate requests like that going forward.

**Key phrase:** "I need to be as transparent about my intent as the other person needs to be to actually trust it — not just what I think is sufficient — and to empathize with their position before I make a request that touches something they own."

---

## Section 3: Cisco IOS knowledge

### "Walk me through your Cisco IOS experience"

**Your honest framing (say this once, clearly, then move to substance):**

> My production platforms have been HP Aruba and Fortinet, so the operational instincts are there. I've been building Cisco IOS fluency through the CCNA curriculum and Packet Tracer labs — interface configuration, VLAN trunking, OSPF neighbor setup, ACLs. The CLI syntax is different but the underlying concepts transfer directly. For anything I haven't touched in production, I'd validate in a lab before applying to a live network — which is the same approach I'd take on any unfamiliar platform.

**Do not just say "I'm studying" — pivot to specifics immediately.**

---

### "Show me how you'd configure a trunk port" (or similar IOS task)

```
interface GigabitEthernet0/1
  switchport mode trunk
  switchport trunk allowed vlan 10,20,30
  switchport trunk native vlan 99
```

**Talk through it:** "I'm setting the port to trunk mode, specifying which VLANs to allow so I'm not flooding the trunk with VLANs that don't need to traverse it, and setting the native VLAN to an unused ID to prevent VLAN hopping."

---

### "What show commands do you use most?"

Lead with the ones you'd reach for first, not a memorized list:

| Command                     | When you'd use it                                      |
| --------------------------- | ------------------------------------------------------ |
| `show ip interface brief`   | First thing — are all interfaces up?                   |
| `show interfaces gi0/0`     | Input/output errors suggest physical or duplex issues  |
| `show vlan brief`           | Confirm port-to-VLAN assignments                       |
| `show interfaces trunk`     | Confirm VLANs are passing on trunk ports               |
| `show ip route`             | Is the route present? Is the next-hop correct?         |
| `show cdp neighbors detail` | Map connected devices with IPs                         |
| `show lldp neighbors`       | Same, but open standard — works with non-Cisco         |
| `show spanning-tree`        | STP topology — check for blocked or inconsistent ports |
| `show ip ospf neighbor`     | Are OSPF adjacencies up?                               |
| `show mac address-table`    | Which port is a specific MAC address on?               |

---

### "How do OSPF neighbors form? What would you check if they're not?"

**Answer:**

OSPF neighbors form when two routers exchange Hello packets and agree on: same area ID, same Hello/Dead timers, same subnet and mask, same network type, and authentication if configured. On a broadcast network like Ethernet, they elect a DR (Designated Router) and BDR (Backup Designated), then form Full adjacency with those.

**If neighbors won't form, I'd check in this order:**

1. `show ip ospf neighbor` — any entry at all? If nothing, packets aren't reaching the neighbor.
2. `show ip ospf interface gi0/0` — is the interface in the right OSPF process and area?
3. Check Hello/Dead timers match on both sides.
4. Check same area ID configured on both interfaces.
5. Check for `passive-interface` — a passive interface sends no Hellos.
6. Check network type matches (point-to-point vs. broadcast changes DR election behavior).
7. Check no ACL is blocking 224.0.0.5 (AllSPFRouters multicast).

---

### "What's the difference between OSPF and EIGRP?"

> OSPF is an open standard, link-state protocol — every router builds a complete map of the network and runs Dijkstra's to find the shortest path. EIGRP is Cisco-proprietary, uses a hybrid approach with the DUAL algorithm, and converges faster in some topologies because feasible successors (pre-calculated backup routes) can promote instantly without a full recalculation. OSPF scales better in large heterogeneous networks; EIGRP is simpler to configure in a homogeneous Cisco environment.

---

### "Have you worked with BGP?"

> I understand BGP at the conceptual level — AS (Autonomous System) numbers, eBGP (external BGP) between different autonomous systems, iBGP (internal BGP) within an AS, and path selection using attributes like AS path and local preference rather than a metric. I haven't administered a BGP session in production. At VCA we're actually dual-ISP — AT&T fiber as primary, Spectrum as failover — but that failover is handled through the Fortinet's SD-WAN and policy-based routing rather than BGP, since neither circuit is set up for provider-side peering. For a campus setup where BGP is genuinely in play for ISP multihoming, I'd work from documentation and test thoroughly in a lab before any production change.
>
> Familiar with SD-WAN technologies like VeloCloud, which is what we use to create secure network tunnel from our remote offices to HQ to allow end user access to internal resources (VM's + File servers)

---

## Section 4: IT and network fundamentals

### "How would you build a campus network from scratch?"

**Answer framework (speak this conversationally — don't list it robotically):**

> I'd start with requirements before touching hardware. How many users, how many buildings, what services need network access — VoIP, wireless, IoT, guest access? That drives the VLAN design and IP addressing, which I'd document before any device gets configured.
>
> For a college campus like this, I'd use a two-tier design — a redundant distribution/core layer and access switches in each building. Access switches handle end devices: PoE for phones and APs, VLAN assignment per port, portfast and bpduguard on access ports. Distribution handles inter-VLAN routing via SVIs, HSRP for gateway redundancy so a single switch failure doesn't take down a VLAN, and OSPF if there's any routing complexity between buildings.
>
> Wireless would be trunked to the distribution layer, with SSIDs mapped to VLANs — staff, faculty, student, and guest all separate. VoIP needs its own VLAN with QoS — DSCP EF marking for voice traffic, LLQ to give it priority queuing, and the switch ports configured with a voice VLAN alongside the data VLAN.
>
> Before I touched a live network I'd document the IP addressing scheme, VLAN table, and physical topology. And I'd set up config backup automation — Oxidized pulling configs to a Git repo on a schedule — before anything goes into production.

**Follow-up they'll likely ask:** "What would you prioritize if the budget was limited?" Answer: distribution redundancy first (a single distribution switch failure takes everything down), then config backup automation, then access layer improvements.

---

### "How do you troubleshoot a connection outage?"

**Answer:**

> I work bottom-up — physical layer first, then Data Link, then Network, then up the stack.
>
> Start at the physical: is the interface up? `show interfaces` will show you errors, CRC counts, input drops. A lot of errors suggests a bad cable or duplex mismatch. No link at all suggests a physical issue — cable, SFP, port.
>
> Data Link: is the device on the right VLAN? `show mac address-table` to confirm the MAC is where I expect it. `show interfaces trunk` to confirm the VLAN is allowed on any trunk in the path.
>
> Network: does the routing table have the right entry? `show ip route` on each L3 device in the path. `ping` from the switch or router to isolate where it breaks. `traceroute` to see exactly which hop drops the packet.
>
> If all that's clean, it moves to the application layer — is the service running, is DNS resolving correctly, is a firewall rule blocking the specific port?

**Real example to tie in:** "I used this approach on the UAG bottleneck at VCA — started by ruling out client-side and network-layer issues before landing on the application/infrastructure layer."

---

### "How would you explain a highly technical issue to non-technical staff?"

**What they're really asking:** Can you communicate with faculty, administrators, and executive staff who aren't IT people but who need to understand what happened and what you're doing about it.

**Answer framework:**

> I lead with impact, not cause. Non-technical staff don't need to understand LLDP — they need to know whether their phones are working, when they'll work, and whether anything they need to do. I give them those three things first.
>
> Then I translate the cause into something that maps to something they already understand. For the IP phone issue, I'd say: "The switch port had a miscommunication with the phone about which network to connect to — like a handshake that wasn't completing. We corrected the instruction set on the switch and it resolved." That's accurate without being a lecture.
>
> I also follow up in writing so people have a record of what happened and what was done. It avoids repeat questions and builds trust that things are being handled.

**Specific Whittier context:** A college has faculty who are not technical but who have strong expectations. Dean's office, admissions, financial aid — these are the stakeholders you'll need to communicate with. Show that you understand that dynamic.

---

### "Tell me about a time you had conflict with another employee" / "What did you do when there was conflict with a coworker?"

**What they're assessing:** Whether you can handle interpersonal friction professionally, de-escalate rather than dig in, and take a real learning point away rather than just describing how you were right.

**Your answer:**

> This came up during a project where we were scoping a potential migration of a recently acquired company's production repos onto a self-hosted Git instance, so everything could be managed more consistently going forward. It was still exploratory on our side — no migration had been approved, we were just assessing feasibility.
>
> As part of that, I requested an access token from their team so I could look at the repo structure. To me it was a routine, low-stakes ask. But from their side, someone outside their team requesting elevated access to their production repos looked like we were trying to take over and potentially put their deployments at risk. That's a completely reasonable read if you don't have the context I had.
>
> It escalated enough that the conversation got moved up to both of our managers, who clarified the intent and scope, and it got smoothed over from there.
>
> What I took away from it: I need to be as transparent about my intent as the other person needs to be to actually trust it, not just what I think is sufficient, and to put myself in their position before I make a request that touches something they own. Especially right after an acquisition, people are already on edge about losing control of their systems, so the burden's on me to lead with the "why" before the "what."

**Key phrase:** "Access requests read very differently depending on which side of an acquisition you're on. Leading with the intent, not just the ask, would have prevented the whole thing."

---

### "What does good network documentation look like to you?"

> Documentation needs to be useful to someone who wasn't there when the decision was made — which might be a future you, a colleague covering for you, or a vendor during an incident. I focus on three things: the topology (physical and logical), the change log (what was done, when, and why), and the runbooks (how to do the common tasks).
>
> For configuration backup specifically, I'd automate it. Oxidized or RANCID pulling configs to a Git repository means every change shows up as a diff, which doubles as an audit trail. At VCA I use that same version-control approach for infrastructure changes.

---

### "How would you go about updating a network appliance?" / "Walk me through a switch or router upgrade"

**What they're assessing:** Whether you treat firmware/IOS upgrades as risky infrastructure changes that require planning, or as something you just run and hope for the best.

**Your answer:**

> I'd never upgrade a production network appliance without a maintenance window and a rollback plan. The steps I follow:
>
> First, pre-work. I capture the current state before touching anything — `show version` for the current IOS version, `show running-config` saved externally via SCP, and a note of what's currently working so I have a baseline to compare against after.
>
> Then I download the correct image from the vendor, verify the MD5 or SHA hash against what the vendor published, and copy it to flash with `copy scp: flash:` or `copy tftp: flash:`. I confirm the file is there and the right size with `dir flash:` before I do anything else.
>
> I set the boot variable to point to the new image — `boot system flash:/<new-image>.bin` — save the config, then schedule the reload for the maintenance window. Before the window, I notify whoever needs to know that there'll be a brief outage.
>
> After the reload: `show version` to confirm the new image is running, ping tests across the network, check OSPF neighbors if applicable, check VLANs, review logs for anything unexpected. If something's wrong, I boot back to the previous image — either by resetting the boot variable or using `software install rollback` on IOS-XE install mode devices.
>
> The rollback plan has to exist before the upgrade starts, not after something breaks.

**Real example to tie in:** The Fortinet rollback story from VCA — same principle. Documented the before state, made the change, something went wrong, reverted immediately because the context was there.

**Follow-ups to prepare for:**

- "What if the device doesn't come back up after the reload?" — console access is your out-of-band recovery. If you don't have console access, you need ROMMON or physical access to recover.
- "Have you done this on a live production device?" — honest answer: Fortinet firmware upgrades at VCA, not Cisco IOS specifically. Same discipline applies.

---

### "How do you think about disaster recovery for network infrastructure?" / "What's your DR plan for the campus network?"

**What they're assessing:** Whether you think proactively about failure modes before they happen, or whether you only react after things break. This is an infrastructure ownership question — they want to know you'll keep the campus connected when something goes wrong.

**Answer framework (spoken conversationally):**

> DR for network infrastructure starts with understanding what your failure scenarios actually are, then making sure you have a recovery path for each one before you need it.
>
> For a campus network I'd think about three main categories: device failure, connectivity failure, and configuration failure. They each require different preparation.

**Then walk through the scenarios:**

> **Device failure — core switch goes down.** This is the highest-impact failure on a campus network. If you're running a single core switch, that's a single point of failure for every VLAN. The mitigation is distribution-layer redundancy: two distribution switches with HSRP for gateway redundancy so a single device failure doesn't take down a subnet. For the core itself, you'd want a hot spare on-site with a known-good config backed up externally, so recovery is "pull the spare, restore from backup, reconnect" rather than a procurement exercise in the middle of a crisis.
>
> **Connectivity failure — ISP outage.** If the campus has a single ISP circuit, you're down until they restore it. The options are: a secondary circuit with failover routing (BGP or policy-based routing if you have two ISPs), or a cellular failover device as a lower-cost backup for critical functions. At minimum, I'd want to know exactly who to call at the ISP, what the SLA is, and have that in writing somewhere the whole team can find it — not just in my head.
>
> **Configuration failure — corruption or bad change.** This is the one I can most directly prevent. Configuration backup automation means that even if someone pushes a bad change or a device loses its config on a bad reload, you have a restore point. I'd use Oxidized or equivalent to pull configs to a Git repo on a scheduled basis. Every change shows up as a diff. If something breaks, I know exactly what changed and I can restore a known-good state.

**What your DR plan looks like in practice:**

> For each critical device I'd want documented: the current config backed up externally, the steps to restore it, and the out-of-band access method — console access or an OOB management VLAN — so if the device goes dark I still have a way in. That runbook lives somewhere the whole team can reach, not on a laptop that goes home with me.

**Incident communication:**

> When something is down, people want two things: to know you're aware of it, and to know when it'll be back. I try to give an initial notification within the first few minutes — "we're investigating, here's what we know" — and then update on a consistent cadence even if the update is just "still working on it." Silence during an outage is worse than imperfect information.
>
> For a campus the stakeholder list matters: IT director first, then department leads for whoever's affected. I keep a contact list for that reason — during an incident is not the time to be hunting for email addresses.

**Your real example to tie in:**

> The Fortinet change at VCA is the small version of this — I had a rollback plan before I started the change, so when something went wrong the recovery was minutes, not hours. The discipline is the same at any scale: know what you'll do before you need to do it.

**High-probability follow-ups:**

- **"Have you ever dealt with a major outage?"** — Lean on the Fortinet rollback (scale it honestly: minutes, not hours, because prep was in place) and the UAG diagnosis. The principle is the same as a larger incident.
- **"What do you do if you can't reach the device remotely?"** — Out-of-band access: console cable directly, OOB management VLAN, or physical access to the device. Remote management stops working precisely when you need it most — you plan for that.
- **"What's your backup strategy for network configs?"** — Oxidized to Git repo, automated pulls on a schedule, diff-based audit trail. Config changes are commits.

---

### "What are your thoughts on AI?" / "How do you use AI in your work?"

**What they're assessing:** Whether you have a grounded, practical relationship with AI tools or an uncritical one — colleges are cautious about data governance, and they want to know you won't put institutional data at risk chasing convenience.

**Your answer (spoken conversationally):**

> I see it as a tool, not a replacement for judgment — especially in infrastructure. Day to day it's most useful for automating the mundane and tedious: drafting scripts, spotting patterns in log output, or getting a first pass at documentation that I then verify and rewrite myself. It's also sped up how I close knowledge gaps — working across Fortinet, Aruba, and now Cisco IOS for the CCNA, it helps me translate concepts between vendor syntaxes faster than digging through three separate sets of documentation, and it's useful for scaffolding scripts or tooling I wouldn't otherwise have time to build from scratch.
>
> Where I draw a line is generative AI for anything creative — that's a human domain, and I don't think a model should be doing the artistic or original-thinking part of someone's job. On the infrastructure side, I'm careful about data privacy specifically: I won't put network topology, configs, or credentials into a public LLM. Privately owned models still mean your data is sitting on someone else's infrastructure, so anything sensitive gets genericized first or kept out entirely — the same discipline I'd apply to any third-party tool that touches internal data.
>
> Bottom line: it speeds up the mechanical parts of the job, but the validation, the judgment calls, and anything that touches production still go through me.

**Real example to tie in:** Studying for the CCNA, I've used AI to sanity-check why an OSPF adjacency wasn't forming or to explain an unfamiliar IOS error message before I dug into the Cisco docs myself — same "verify before you trust it" discipline I'd apply to anything AI-assisted that touches a live network.

**Follow-ups to prepare for:**

- **"Would you use AI to help write network configs?"** — For drafting or explaining syntax, yes. For anything going into production, no — same as anything untested: it gets validated in a lab first, same discipline as the Cisco gap answer.
- **"How would you handle a staff or faculty member wanting to use AI tools with sensitive data?"** — That's a policy and awareness conversation as much as a technical one: know what's allowed under the college's data governance policy, and make sure people understand that anything typed into a public LLM should be treated as potentially non-confidential.

---

### "What would your first 30 days look like here?"

> Discovery first. I'd run `show cdp neighbors detail` and `show lldp neighbors` on the core and distribution switches to map what's connected and where. Pull routing tables, VLAN tables, and all configs into a Git repo. Get SNMP monitoring set up if it isn't already — either with what's in place or with something like LibreNMS.
>
> I'd also talk to the people who know the history: whoever managed this network before, the helpdesk staff who field the calls when things break. The informal knowledge — what's a known issue, what was built as a workaround — is as important as the configs.
>
> By day 30 I'd want a physical and logical topology diagram, a complete VLAN and IP address table, and a list of the things that need attention — not to have fixed them, but to understand the order of priority.

---

## STAR stories (pre-prepared, adaptable)

### STAR 1: IP phone LLDP fix (VoIP, VLAN, layer 2 troubleshooting)

See Story A above. Use for: troubleshooting questions, VoIP questions, "tell me about a recent technical problem."

### STAR 2: Fortinet rollback (change management, documentation, incident response)

See Story B above. Use for: "tell me about a time something went wrong," "how do you manage risk during changes," "why is documentation important."

### STAR 3: UAG bottleneck (systematic troubleshooting, performance diagnosis)

See Story C above. Use for: "how do you troubleshoot a network issue," "describe your diagnostic approach," "tell me about a time you had to dig into a performance problem."

### STAR 4: DMZ connector (security, network design decision)

See Story D above. Use for: "tell me about a network design decision you made," "how do you think about network security," "describe a time you had to balance access with security."

### STAR 5: BitLocker rollout at Five Acres (scale, coordination, regulated environment)

- **Situation:** 150+ Windows machines in a healthcare environment needed BitLocker encryption across two business days.
- **Task:** Coordinate the rollout without disrupting clinical operations.
- **Action:** Staged the deployment by department, coordinated with IT leads at each location, communicated the schedule to department heads so they knew when their devices would be briefly unavailable.
- **Result:** 150+ machines encrypted in 2 business days. No service disruption complaints.
- **Use for:** "Tell me about managing a large-scale change," "how do you coordinate with stakeholders," "tell me about a time you had time pressure."

### STAR 6: Access token conflict during acquisition scoping (interpersonal conflict, cross-team communication)

See Story E above. Use for: "tell me about a conflict with a coworker," "tell me about a time you disagreed with someone," "how do you handle interpersonal friction."

---

## Questions for you to ask

### For the IT Network Systems Director

**1. "What does the network infrastructure look like today — how is it tiered, and what's the mix of hardware?"**

- Why ask: Shows you're already thinking about what you'd be inheriting. Signals that you know what questions to ask.
- Listen for: Scale, complexity, any known technical debt, Cisco vs. mixed environment.

**2. "What did the previous person in this role do well, and where were the gaps they left?"**

- Why ask: Honest answer tells you what the real expectations are, and what problems you'd walk into.
- Listen for: If they struggle to answer, the role may not be well-defined. If they're candid, that's a good sign.

**3. "The CCNA covers the concepts, but I'd be learning your specific environment on day one. What's the biggest technical gap you'd expect someone to need time to close?"**

- Why ask: Shows self-awareness and proactive thinking. Invites them to be honest about complexity.
- Listen for: Whether they have a realistic picture of the onboarding curve.

**4. "How does the network team interact with the broader IT team here? Is this a solo network role or are there other people touching infrastructure?"**

- Why ask: Critical for understanding scope, support, and escalation paths.
- Listen for: Whether you'd have backup for on-call or vacations, or whether you're the single point of failure.

**5. "What's the most urgent project or problem that needs attention in the first few months?"**

- Why ask: Shows you want to contribute, not just settle in. Gives you something to follow up on post-interview.
- Listen for: Anything that suggests the network is in poor shape vs. normal ongoing work.

---

## Potential concerns and how to address them

### Concern 1: Cisco IOS operational experience gap

**If raised:** "You haven't actually administered Cisco in production."

**Your response:**

> That's accurate, and I'd rather be direct about it than oversell it. My production platforms have been HP Aruba and Fortinet. The CCNA is my direct response to that gap — it forces Cisco IOS fluency through structured curriculum and hands-on labs. The troubleshooting approach and the underlying protocols are the same regardless of vendor. I'd validate anything Cisco-specific in a lab before applying it to a live network here, which is the same discipline I apply at VCA when touching anything I haven't done before.

**Do not say:** "I know Cisco well" — they will ask follow-up questions that will expose the gap. Honest framing is more credible.

---

### "Why are you leaving your current role?" / "Why Whittier specifically?"

**What they're assessing:** Whether you're running toward something or away from something. Whether you'll stay.

**Your answer:**

> A few things, honestly. The work at VCA has given me a solid foundation across networking, systems, and security — but the structure there is intentionally generalist. My director's goal is for me to cover all fronts, so I'm spread across endpoint management, identity, VoIP, and networking rather than going deep on any one of them. The networking is the part I want to specialize in, and this role is that opportunity: dedicated network ownership on a campus where the infrastructure actually drives the organization.
>
> The commute is also a real factor. I'm currently doing about two hours round trip. Whittier is under an hour from where I live. That's not a small thing — it means more energy for the actual work, and it means I'm more likely to be genuinely present rather than just grinding through the day. I'm transparent about that because I think it matters for whether someone stays in a role long-term.

**Key principle:** Lead with the specialization narrative — generalist by necessity, specialist by choice. The commute follows as an honest practical reason that reinforces retention. Don't lead with commute.

**What to listen for from them:** If they ask follow-up questions about your commute or where you live, that's actually a good sign — they're thinking about whether you'd stick around.

---

### Concern 2: Third application — what's actually different?

**If raised:** "We've interviewed you twice. Why should this time be different?"

**Your response:**

> Two things are materially different. The first is the CCNA — I'm completing it in August, which directly addresses the Cisco gap from the last interview. The second is that the scope at VCA has grown — I've been dealing with more complex network issues than I had when I interviewed last time, and I can speak to specific problems I've solved that I couldn't have talked about before. The role is still the right target. I'm just better positioned for it now.

---

### Concern 3: Campus vs. enterprise environment experience

**If raised:** "You've worked in enterprise/corporate settings, not education."

**Your response:**

> The infrastructure fundamentals are the same — VLANs, routing, PoE, wireless, security policy — but the stakeholder mix is different. A college has faculty, students, administration, and guests all on the same campus with different needs and different expectations for how IT communicates with them. I've had to calibrate communication differently depending on whether I'm talking to a VP, an end user, or a vendor, and I'd apply that same awareness here.

---

## Study plan: July 14–23

**Interview:** Thursday July 23, 9:30am
**Vacation:** Friday July 18 – Sunday morning July 20 (limited study only)
**Approach:** Front-load the heavy technical work Tuesday–Thursday while you have full evenings. Use vacation time for light review only — doc on your phone, no Packet Tracer. Come back Monday with two solid days for a mock and tightening.

---

### Tuesday July 14 (tonight) — Full read-through

- [ ] Read the entire document once, cover to cover
- [ ] Goal: know what sections exist and roughly where your answers live — not memorization yet

### Wednesday July 15 — Introduction and STAR stories

- [x] Practice "tell me about yourself" out loud, timed at 2 minutes
- [x] Say each of Stories A–D out loud — focus on the key phrase at the end of each
- [x] Practice the "why are you applying again" and "why are you leaving" answers out loud

### Thursday July 16 — Cisco IOS

- [x] Cover the show commands table — for each one, say out loud what it tells you and when you'd reach for it
- [x] Packet Tracer: configure a trunk port from scratch, verify with `show interfaces trunk` and `show vlan brief`
- [x] Practice the trunk port config answer and OSPF neighbor formation answer verbally

### Friday July 18 – Sunday morning July 20 — Vacation (light, phone-friendly)

- [x] Fri or Sat: reread the campus design and troubleshooting sections — no drilling, just absorb
- [x] Sat or Sun morning: reread the DR section and appliance upgrade section
- [ ] Sun morning: pick your 3 questions to ask — commit to them now so they're not a decision on Monday

### Monday July 21 — Packet Tracer lab + concerns

- [ ] Packet Tracer: build a small multi-layer topology (core → distribution → access), configure VLANs, trunks, SVIs, OSPF between L3 devices — validate with show commands
- [ ] Work through the "potential concerns" section out loud: Cisco gap framing, third application framing

### Tuesday July 22 — Full mock interview (no notes)

- [ ] Run through the full interview start to finish as if it's real: intro, VCA stories, Cisco questions, fundamentals, concerns, your questions
- [ ] Time yourself — should fit in 45–60 minutes
- [ ] Note anything that felt vague or slow; spend 20 minutes drilling those spots afterward

### Wednesday July 23 — Day before (light only)

- [ ] Read through the document once — calm pass, no drilling
- [ ] Confirm logistics: location or video link, parking if in-person
- [ ] Early to bed

### Thursday July 23 — Interview day (9:30am)

- [ ] Morning: reread only the intro answer and your top 2–3 STAR stories — nothing new
- [ ] Arrive 10 minutes early / join the call 2 minutes before
- [ ] Water nearby — you'll be talking for an hour
- [ ] Three breaths before you start

---

## Practical preparation checklist

### Day before

- [ ] Review this document
- [ ] Confirm 3 questions to ask (from the list above)
- [ ] Confirm interview time and location/link

### Day of

- [ ] Arrive 30 minutes early
- [ ] Have CV visible (for reference during stories)
- [ ] Water nearby — you'll be talking
- [ ] Take 3 breaths before joining

---

## Thank-you email template

**Subject:** Thank you — Network Administrator interview

Dear [Name],

Thank you for the time today. I appreciated [reference one specific topic from the conversation — something they said about the network, a question they asked, a detail they shared about the environment].

[One sentence reinforcing fit:] The [specific thing they mentioned, e.g., "scope of the campus infrastructure" or "direction you described for the network team"] aligns closely with what I've been working toward, and I left the conversation more confident that this is the right next step.

I'm happy to provide any additional information. Looking forward to hearing about next steps.

Dylan Nguyen
(626) 559-7499

**Send within 24 hours. Personalize the middle paragraph — a generic thank-you is worse than a specific one.**

---

_Interview Preparation | Network Administrator, Whittier College | Third Application — Round 1 | July 2026_
_Career Helper Plugin | Prosper AI Consulting, UK_
