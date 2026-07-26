# Full Mock Interview — Network Administrator, Whittier College

Companion drill doc to `interview-prep.md`. Two passes: **Part 1** is questions only — run through it cold, out loud, timed. **Part 2** is the same questions paired with your prepared answers — use it to check what you said, or to review before a run.

---

## Part 1: Questions only

### Introduction

1. Tell me about yourself / walk me through your background.
2. Why are you applying again? What's different this time?

### What you've been up to (behavioral / STAR)

3. What have you been working on recently? / Tell me about a recent technical problem.
4. Tell me about a time something went wrong.
5. How do you troubleshoot a network issue? Describe your diagnostic approach.
6. Tell me about a network design decision you made.
7. Tell me about a conflict with a coworker, or a time you disagreed with someone.
8. Tell me about managing a large-scale change, or a time you had time pressure.

### Cisco IOS knowledge

9. Walk me through your Cisco IOS experience.
10. Show me how you'd configure a trunk port.
11. What show commands do you use most?
12. How do OSPF neighbors form? What would you check if they're not forming?
13. What's the difference between OSPF and EIGRP?
14. Have you worked with BGP?

### IT and network fundamentals

15. How would you build a campus network from scratch?
16. Follow-up: What would you prioritize if the budget was limited?
17. Follow-up: Why collapsed core instead of a full 3-tier design? Wouldn't 3-tier make sense for a campus this size?
18. How do you troubleshoot a connection outage?
19. How would you explain a highly technical issue to non-technical staff?
20. What does good network documentation look like to you?
21. How would you go about updating a network appliance? Walk me through a switch or router upgrade.
22. Follow-up: What if the device doesn't come back up after the reload?
23. Follow-up: Have you done this on a live production device?
24. How do you think about disaster recovery for network infrastructure? What's your DR plan for the campus network?
25. Follow-up: Have you ever dealt with a major outage? Fortinet Denver, VDI lost from SAN failure
26. Follow-up: What do you do if you can't reach the device remotely? Off band
27. Follow-up: What's your backup strategy for network configs?
28. What are your thoughts on AI? How do you use AI in your work?
29. Follow-up: Would you use AI to help write network configs?
30. Follow-up: How would you handle a staff or faculty member wanting to use AI tools with sensitive data?
31. What would your first 30 days look like here?

### Supplemental technical fundamentals

32. Walk me through subnetting a /24 into 4 equal subnets.
33. Explain Spanning Tree Protocol — why does it exist, and what are the port roles?\*
34. Walk me through the DHCP process. How would you troubleshoot a client not getting an IP?
35. How does DNS resolution work? How would you troubleshoot "the site won't load"?
36. Explain the types of NAT.
37. Name the port number for: SSH, DNS, HTTP, HTTPS, RDP, SNMP, BGP.
38. What's the difference between 2.4GHz and 5GHz wireless?
39. How would you secure access-layer ports on campus?
40. Explain HSRP and VRRP.

### Job-description-specific topics

41. Explain IPv6 addressing — how is it different from IPv4?
42. Have you deployed IPv6 in production?
43. Explain GRE, IPsec, and DMVPN.
44. Explain multicast — what are IGMP and PIM for?
45. What's the difference between NAC and SDP?
46. What's the difference between RADIUS and TACACS+?
47. Tell me about the campus cable plant — what standards and considerations matter?
48. Have you trained or supervised anyone?
49. Tell me about a time you had to put together a cost analysis or proposal.
50. How comfortable are you with Linux or Mac administration?
51. Are you available for off-hours work or a flexible schedule?

### Potential concerns

52. You haven't actually administered Cisco in production.
53. Why are you leaving your current role? Why Whittier specifically?
54. We've interviewed you twice. Why should this time be different?
55. You've worked in enterprise/corporate settings, not education.

### Closing

56. What questions do you have for me?

---

## Part 2: Questions with answers

### Introduction

**1. Tell me about yourself / walk me through your background.**

> I've been continuing my work as a systems and network admin at VCA Consultants. Since I joined, our user base has grown and management scope has expanded to 2 office sites plus a large remote workforce. I've gotten more involved with the physical and virtual networking infrastructure — firewall rules, access switch configuration, VMware virtual switch config, VLAN management — alongside my usual IT responsibilities: administering our VDI, remote endpoints, user deployment, and VMware server infrastructure. I made an effort to be more involved and aware of the internal network, but my responsibilities are broad by design.
>
> The reason I keep coming back for this role is that I want to go deep on the network side specifically. At VCA I cover a lot of ground, but the breadth of the role means I can't specialize. I hear online and amongst my peers that no one really likes to deal with the network, but to me, I see it as an opportunity to push myself and take the path least treaded. That and an opportunity to take ownership of something that can both impact and empower hundreds of people (students, and faculty alike).
>
> Since we last spoke, the biggest change is my progress on the CCNA. I'm wrapping up coursework this month and sitting the exam in late August. I've been running Packet Tracer labs and applying what I'm learning, making the connections between the theoretical with the practical applications in our production infrastructure. Continuing to learn and grow, and even more focused on empowering users through tech, when given the opportunity.

**2. Why are you applying again? What's different this time?**

> Honestly, the honest answer from the last interview was that my Cisco IOS experience was superficial. Since picking up my studies for the CCNA I force myself to go beyond knowing the concepts and actually work with lab based and production side configurations. I've been practicing in Packet Tracer: OSPF neighbor setup, VLAN trunking, ACLs, interface configuration. And at VCA the network scope has grown, so I'm coming in with more production troubleshooting behind me than I had last time.

---

### What you've been up to (behavioral / STAR)

**3. What have you been working on recently?** — _IP phone LLDP fix_

> Situation: Rolling out Poly Edge E500 IP phones across the local office on Zoom Phone. Deployment stalled — half the office phones wouldn't complete one-touch provisioning to the Zoom provisioning server.
> Task: Diagnose and resolve the issue without disrupting the rest of the office.
> Action: Worked with our IT Director to check the phone configs, port configs, and VLAN assignments first — those all checked out. Dug into the HP Aruba switch's configuration options next, working through the CLI with help from ChatGPT and Zoom's documentation for reference. Found that LLDP wasn't enabled on the switch, confirmed against HP Aruba's own documentation. Toggled LLDP on.
> Result: Phones immediately connected to the Zoom provisioning server and completed one-touch deployment. Root cause documented so LLDP is enabled by default on any new phone port configuration going forward.
>
> Key phrase: "The protocols tell you exactly what should be happening — the diagnostic work is just matching what you're seeing to what the protocol says should be true."

**4. Tell me about a time something went wrong.** — _Fortinet rollback_

> Situation: Mid-change on the Fortinet firewall — adding a new rule to enable a department service. Site-to-site connectivity to the Denver office dropped.
> Task: Restore service as fast as possible, understand what happened.
> Action: Because I document changes as I go — what the rule is, what it's supposed to do, what the before state was — I had the context immediately. Reverted the new rule. Denver connectivity restored within minutes. Then reviewed what the interaction was between the new rule and the existing policies, fixed the ordering, tested again.
> Result: Total outage was under 5 minutes. No ticket needed from Denver — I reached out to confirm restoration before they noticed.
>
> Key phrase: "A configuration mistake is recoverable. A configuration mistake with no documentation is a crisis."

**5. How do you troubleshoot a network issue? Describe your diagnostic approach.** — _UAG bottleneck_

> Situation: Remote staff started reporting session latency on VMware Horizon VDI. Not all users, not consistent.
> Task: Identify whether this was a client-side, network, or server-side issue.
> Action: Started at the edge — checked whether latency correlated with specific users, times, or sites. Didn't. Traced the connection path from external client through the UAG (Unified Access Gateway) into the internal Horizon infrastructure. Compared client-side latency logs against UAG session throughput metrics. Found the UAG was hitting CPU saturation under concurrent session load. Recommended and implemented a resource increase on the UAG VM; monitored for recurrence.
> Result: Latency complaints stopped. Added UAG CPU utilization to the monitoring dashboard.
>
> Key phrase: "I followed the connection path methodically. The UAG is the chokepoint between outside and inside, so that's where I looked once client-side and server-side checked out."

**6. Tell me about a network design decision you made.** — _DMZ connector server_

> Situation: External devices needed to reach the internal management network for administration — but opening the perimeter directly was not acceptable.
> Task: Enable the access without creating a firewall hole into the internal network.
> Action: Configured a secure connector server in the DMZ. External devices connect to the DMZ host; the DMZ host has a restricted, encrypted connection to the internal management VLAN. Nothing from outside reaches the internal network directly.
> Result: External administration capability without perimeter exposure. Firewall policy documented with the rationale for the DMZ architecture.

**7. Tell me about a conflict with a coworker, or a time you disagreed with someone.** — _Access token conflict during acquisition scoping_

> Situation: VCA was scoping a potential migration of a recently acquired company's production repos to a self-hosted Git instance. It was exploratory only — no migration had been approved.
> Task: Assess feasibility without disrupting the acquired company's existing deployment pipeline or overstepping into systems that weren't mine yet.
> Action: I requested an access token from their team so I could look at repo structure. To me it was routine, low-stakes exploratory access. From their side, an outside admin requesting elevated access to their production repos looked like an attempt to take over and put their deployments at risk — a reasonable read if you don't have the context I had. It escalated to the point that the conversation got moved up to both of our respective managers, who clarified intent and scope, and things were smoothed over from there.
> Result: Scoping continued collaboratively. More importantly, I walked away with a concrete lesson about how I initiate requests like that going forward.
>
> Key phrase: "I need to be as transparent about my intent as the other person needs to be to actually trust it — not just what I think is sufficient — and to empathize with their position before I make a request that touches something they own."

**8. Tell me about managing a large-scale change, or a time you had time pressure.** — _BitLocker rollout at Five Acres_

> Situation: 150+ Windows machines in a healthcare environment needed BitLocker encryption across two business days.
> Task: Coordinate the rollout without disrupting clinical operations.
> Action: Staged the deployment by department, coordinated with IT leads at each location, communicated the schedule to department heads so they knew when their devices would be briefly unavailable.
> Result: 150+ machines encrypted in 2 business days. No service disruption complaints.

---

### Cisco IOS knowledge

**9. Walk me through your Cisco IOS experience.**

> My production platforms have been HP Aruba and Fortinet, so the operational instincts are there. I've been building Cisco IOS fluency through the CCNA curriculum and Packet Tracer labs — interface configuration, VLAN trunking, OSPF neighbor setup, ACLs. The CLI syntax is different but the underlying concepts transfer directly. For anything I haven't touched in production, I'd validate in a lab before applying to a live network — which is the same approach I'd take on any unfamiliar platform.

**10. Show me how you'd configure a trunk port.**

```
interface GigabitEthernet0/1
  switchport mode trunk
  switchport trunk allowed vlan 10,20,30
  switchport trunk native vlan 99
```

> I'm setting the port to trunk mode, specifying which VLANs to allow so I'm not flooding the trunk with VLANs that don't need to traverse it, and setting the native VLAN to an unused ID to prevent VLAN hopping.

**11. What show commands do you use most?**

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

**12. How do OSPF neighbors form? What would you check if they're not forming?**

> OSPF neighbors form when two routers exchange Hello packets and agree on: same area ID, same Hello/Dead timers, same subnet and mask, same network type, and authentication if configured. On a broadcast network like Ethernet, they elect a DR and BDR, then form Full adjacency with those.
>
> Checklist, in order: `show ip ospf neighbor` (any entry at all?), `show ip ospf interface gi0/0` (right process/area?), Hello/Dead timers match, same area ID, check for `passive-interface`, check network type matches, check no ACL is blocking 224.0.0.5.

**13. What's the difference between OSPF and EIGRP?**

> OSPF is an open standard, link-state protocol — every router builds a complete map of the network and runs Dijkstra's to find the shortest path. EIGRP is Cisco-proprietary, uses a hybrid approach with the DUAL algorithm, and converges faster in some topologies because feasible successors (pre-calculated backup routes) can promote instantly without a full recalculation. OSPF scales better in large heterogeneous networks; EIGRP is simpler to configure in a homogeneous Cisco environment.

**14. Have you worked with BGP?**

> I understand BGP at the conceptual level — AS numbers, eBGP between different autonomous systems, iBGP within an AS, and path selection using attributes like AS path and local preference rather than a metric. I haven't administered a BGP session in production. At VCA we're dual-ISP — AT&T fiber as primary, Spectrum as failover — but that failover is handled through the Fortinet's SD-WAN and policy-based routing rather than BGP, since neither circuit is set up for provider-side peering. For a campus setup where BGP is genuinely in play for ISP multihoming, I'd work from documentation and test thoroughly in a lab before any production change.
>
> Familiar with SD-WAN technologies like VeloCloud, which is what we use to create secure network tunnels from our remote offices to HQ to allow end user access to internal resources.

---

### IT and network fundamentals

**15. How would you build a campus network from scratch?**

> I'd start with requirements before touching hardware. How many users, how many buildings, what services need network access — VoIP, wireless, IoT, guest access? That drives the VLAN design and IP addressing, which I'd document before any device gets configured.
>
> For a college campus like this, I'd use a collapsed-core (two-tier) design — a redundant distribution/core layer and access switches in each building. Access switches handle end devices: PoE for phones and APs, VLAN assignment per port, portfast and bpduguard on access ports. Distribution handles inter-VLAN routing via SVIs, HSRP for gateway redundancy, and OSPF if there's any routing complexity between buildings.
>
> Wireless would be trunked to the distribution layer, with SSIDs mapped to VLANs — staff, faculty, student, and guest all separate. VoIP needs its own VLAN with QoS — DSCP EF marking, LLQ for priority queuing, voice VLAN alongside the data VLAN.
>
> Before I touched a live network I'd document the IP addressing scheme, VLAN table, and physical topology, and set up config backup automation before anything goes into production.

**16. Follow-up: What would you prioritize if the budget was limited?**

> Distribution redundancy first (a single distribution switch failure takes everything down), then config backup automation, then access layer improvements.

**17. Follow-up: Why collapsed core instead of a full 3-tier design? Wouldn't 3-tier make sense for a campus this size?**

> A dedicated core layer earns its complexity when a single distribution pair can't cleanly aggregate everything — lots of buildings, high inter-building traffic, or distinct blocks that need fault isolation from each other. In a classic 3-tier design the core is kept deliberately dumb and fast — no ACLs, no routing policy — while distribution handles inter-VLAN routing and policy enforcement.
>
> I actually looked at Whittier's campus map before this interview. It's roughly 30 buildings on one contiguous, walkable quad — academic and residential halls clustered tightly together, with the athletics complex just east of the main quad but still on the same footprint, not a separate site. That's one campus block, not a multi-site network. A single redundant distribution/core pair, feeding fiber out to each building's access switch, comfortably aggregates that without a dedicated core layer earning its keep.
>
> If I were thinking about redundancy specifically, I'd treat it as two natural zones — the main academic/residential quad and the athletics cluster — and make sure the fiber paths to each don't share a single point of failure. That's a cabling and resiliency decision, not a reason to add a third switching tier.
>
> One detail worth flagging: Broadoaks School, the K-8 lab school on campus, is functionally a different institution sharing the property — a strong candidate for its own VLAN and tighter ACLs regardless of tier.
>
> So the trigger to flip to 3-tier isn't "it's a college," it's scale. Based on the map, Whittier doesn't hit that bar — but I'd confirm actual switch counts and traffic patterns in the first 30 days before treating that as settled.

**18. How do you troubleshoot a connection outage?**

> I work bottom-up — physical layer first, then Data Link, then Network, then up the stack.
>
> Physical: is the interface up? `show interfaces` for errors, CRC counts, input drops.
> Data Link: is the device on the right VLAN? `show mac address-table`, `show interfaces trunk`.
> Network: `show ip route`, `ping`, `traceroute` to isolate where it breaks.
> If all that's clean, it moves to the application layer — service running, DNS resolving, firewall rule blocking the port.
>
> I used this approach on the UAG bottleneck at VCA — ruling out client-side and network-layer issues before landing on the application/infrastructure layer.

**19. How would you explain a highly technical issue to non-technical staff?**

> I lead with impact, not cause. Non-technical staff need to know whether their phones are working, when they'll work, and whether they need to do anything — I give them those three things first.
>
> Then I translate the cause into something that maps to what they already understand. For the IP phone issue: "The switch port had a miscommunication with the phone about which network to connect to — like a handshake that wasn't completing. We corrected the instruction set on the switch and it resolved."
>
> I follow up in writing so people have a record of what happened. It avoids repeat questions and builds trust that things are being handled.

**20. What does good network documentation look like to you?**

> Documentation needs to be useful to someone who wasn't there when the decision was made. I focus on three things: the topology (physical and logical), the change log (what was done, when, and why), and the runbooks (how to do the common tasks).
>
> For configuration backup specifically, I'd automate it — Oxidized or RANCID pulling configs to a Git repository means every change shows up as a diff, which doubles as an audit trail.

**21. How would you go about updating a network appliance? Walk me through a switch or router upgrade.**

> I'd never upgrade a production network appliance without a maintenance window and a rollback plan.
>
> Pre-work: capture current state — `show version`, `show running-config` saved externally, note of what's currently working.
> Download the correct image, verify the hash, copy to flash, confirm with `dir flash:`.
> Set the boot variable, save the config, schedule the reload for the maintenance window, notify stakeholders beforehand.
> After the reload: `show version`, ping tests, OSPF neighbor checks, VLAN checks, review logs. If something's wrong, boot back to the previous image.
>
> The rollback plan has to exist before the upgrade starts, not after something breaks.

**22. Follow-up: What if the device doesn't come back up after the reload?**

> Console access is your out-of-band recovery. If you don't have console access, you need ROMMON or physical access to recover.

**23. Follow-up: Have you done this on a live production device?**

> Fortinet firmware upgrades at VCA, not Cisco IOS specifically. Same discipline applies.

**24. How do you think about disaster recovery for network infrastructure? What's your DR plan for the campus network?**

> DR starts with understanding what your failure scenarios actually are, then making sure you have a recovery path for each one before you need it. Three categories: device failure, connectivity failure, configuration failure.
>
> **Device failure — core switch down:** distribution-layer redundancy with HSRP, plus a hot spare on-site with a known-good config backed up externally.
> **Connectivity failure — ISP outage:** secondary circuit with failover routing, or cellular failover for critical functions. Know the ISP's SLA and who to call, in writing.
> **Configuration failure — corruption or bad change:** automated config backup (Oxidized) to a Git repo — every change is a diff, every diff is a restore point.
>
> For each critical device: config backed up externally, documented restore steps, out-of-band access method. That runbook lives somewhere the whole team can reach.
>
> On incident communication: people want to know you're aware and when it'll be back. Initial notification within minutes, consistent updates even if the update is "still working on it." For a campus: IT director first, then affected department leads.
>
> The Fortinet change at VCA is the small version of this — rollback plan before I started, so recovery was minutes, not hours.

**25. Follow-up: Have you ever dealt with a major outage?**

> Lean on the Fortinet rollback and the UAG diagnosis, scaled honestly — minutes, not hours, because prep was in place. The principle is the same as a larger incident.

**26. Follow-up: What do you do if you can't reach the device remotely?**

> Out-of-band access: console cable directly, OOB management VLAN, or physical access. Remote management stops working precisely when you need it most — you plan for that.

**27. Follow-up: What's your backup strategy for network configs?**

> Oxidized to Git repo, automated pulls on a schedule, diff-based audit trail. Config changes are commits.

**28. What are your thoughts on AI? How do you use AI in your work?**

> I see it as a tool, not a replacement for judgment — especially in infrastructure. Day to day it's most useful for automating the mundane: drafting scripts, spotting patterns in log output, a first pass at documentation I then verify myself. It's sped up how I close knowledge gaps — working across Fortinet, Aruba, and now Cisco IOS for the CCNA, it helps translate concepts between vendor syntaxes faster than digging through separate documentation.
>
> Where I draw a line is generative AI for anything creative. On the infrastructure side, I'm careful about data privacy — I won't put network topology, configs, or credentials into a public LLM. Anything sensitive gets genericized first or kept out entirely.
>
> Bottom line: it speeds up the mechanical parts of the job, but the validation, judgment calls, and anything touching production still go through me.
>
> Studying for the CCNA, I've used AI to sanity-check why an OSPF adjacency wasn't forming or to explain an unfamiliar IOS error message before digging into the Cisco docs myself.

**29. Follow-up: Would you use AI to help write network configs?**

> For drafting or explaining syntax, yes. For anything going into production, no — same as anything untested: it gets validated in a lab first.

**30. Follow-up: How would you handle a staff or faculty member wanting to use AI tools with sensitive data?**

> That's a policy and awareness conversation as much as a technical one: know what's allowed under the college's data governance policy, and make sure people understand that anything typed into a public LLM should be treated as potentially non-confidential.

**31. What would your first 30 days look like here?**

> Discovery first. `show cdp neighbors detail` and `show lldp neighbors` on the core and distribution switches to map what's connected and where. Pull routing tables, VLAN tables, and all configs into a Git repo. Get SNMP monitoring set up if it isn't already.
>
> I'd also talk to the people who know the history — whoever managed this network before, the helpdesk staff who field the calls when things break. The informal knowledge is as important as the configs.
>
> By day 30: a physical and logical topology diagram, a complete VLAN and IP address table, and a prioritized list of things that need attention.

---

### Supplemental technical fundamentals

**32. Walk me through subnetting a /24 into 4 equal subnets.**

> A /24 gives 256 addresses, 254 usable. To carve it into 4 subnets, borrow 2 bits → /26, giving 4 subnets of 64 addresses (62 usable) each. Formula: usable hosts = 2^(32-prefix) - 2. For 10.10.10.0/24: .0/26, .64/26, .128/26, .192/26.

**33. Explain Spanning Tree Protocol — why does it exist, and what are the port roles?**

> STP prevents Layer 2 loops when there's physical redundancy between switches — without it, a redundant link causes a broadcast storm. It elects a root bridge, then every other switch calculates its lowest-cost path to the root. Port roles: root port (best path to root), designated port (forwards for a segment), blocking/discarding (would create a loop).
>
> Portfast gets end devices online instantly instead of waiting through the STP states. Bpduguard shuts a port down if it receives a BPDU — protection against a rogue switch.

**34. Walk me through the DHCP process. How would you troubleshoot a client not getting an IP?**

> DORA — Discover, Offer, Request, Acknowledge. For a multi-VLAN environment, each VLAN's SVI needs a local scope or an `ip helper-address` pointing at a central DHCP server, since DHCP broadcasts don't cross VLAN boundaries.
>
> Troubleshooting order: right VLAN on the port? `ip helper-address` configured correctly? scope not exhausted? has the client actually sent a discover?

**35. How does DNS resolution work? How would you troubleshoot "the site won't load"?**

> Root servers → TLD servers → authoritative servers, with recursive resolvers doing the lookup on behalf of clients and caching per TTL.
>
> Isolate DNS vs. connectivity first — `nslookup`/`dig` the hostname. Resolves but doesn't connect → routing/firewall. Doesn't resolve → check the DNS server is reachable, the record exists and is correct, check for a stale cache.

**36. Explain the types of NAT.**

> Static NAT: fixed 1:1 mapping, for something needing a consistent public IP. Dynamic NAT: pulls from a pool of public IPs. PAT (NAT overload): many internal hosts share one public IP, distinguished by port — what most networks actually run day to day.

**37. Name the port number for: SSH, DNS, HTTP, HTTPS, RDP, SNMP, BGP.**

> SSH 22, DNS 53, HTTP 80, HTTPS 443, RDP 3389, SNMP 161/162, BGP 179.

**38. What's the difference between 2.4GHz and 5GHz wireless?**

> 2.4GHz: better range and wall penetration, only 3 non-overlapping channels (1, 6, 11), more interference. 5GHz: more non-overlapping channels, higher throughput, shorter range. For a campus: 5GHz-preferred with band steering, higher AP density in dense areas, channel/power planning via a proper site survey.

**39. How would you secure access-layer ports on campus?**

> Combination: port security for basic MAC limiting/rogue-device control, 802.1X where identity-based access control matters, bpduguard/portfast for loop protection. Control what's allowed onto the network by design, not by trust.

**40. Explain HSRP and VRRP.**

> HSRP (Cisco-proprietary) and VRRP (open standard) both let two or more routers/switches share a virtual IP as the default gateway for a subnet. One active, one standby; if active fails, standby takes over the virtual IP within seconds. This is what makes distribution-layer redundancy actually work.

---

### Job-description-specific topics

**41. Explain IPv6 addressing — how is it different from IPv4?**

> 128-bit addresses, 8 groups of hex separated by colons, consecutive zero groups collapsible to `::` once per address. `/64` is the standard LAN prefix — aligning to the addressing model, not conserving space. Address assignment via SLAAC or DHCPv6. Neighbor Discovery replaces ARP. Link-local addresses (`fe80::/10`) auto-assigned on every interface.
>
> Practical differences: no NAT needed in the traditional sense (though NAT66/NPTv6 exists); an interface can hold multiple IPv6 addresses at once; subnetting math is hex/nibble boundaries, not decimal.

**42. Have you deployed IPv6 in production?**

> No, VCA's environment is IPv4-only. Understood at the design level — I'd validate thoroughly in a lab before a production rollout, same discipline as the Cisco gap.

**43. Explain GRE, IPsec, and DMVPN.**

> GRE wraps arbitrary traffic — including routing protocols — in an IP packet to tunnel it point-to-point. Not encrypted on its own. IPsec is the encryption/authentication framework — ESP provides integrity plus encryption (what's actually used almost always). IKE Phase 1 builds a secure management tunnel, Phase 2 negotiates the security associations protecting data traffic. GRE and IPsec are often paired.
>
> DMVPN combines multipoint GRE (one tunnel interface, many peers) with NHRP (dynamic spoke discovery) and IPsec for encryption — lets a hub-and-spoke design build direct spoke-to-spoke tunnels on demand instead of manually configuring a tunnel per site pair.
>
> VCA's dual-ISP failover runs through Fortinet SD-WAN and VeloCloud rather than DMVPN — that's the modern equivalent I actually have hands-on experience with.

**44. Explain multicast — what are IGMP and PIM for?**

> Multicast lets a single stream reach many receivers without duplicating traffic per-recipient. IGMP is how hosts tell their local router they want to join a group — IGMPv3 adds source filtering. PIM is how routers build the distribution tree between each other — sparse mode only sends where there's an explicit request (the common choice), dense mode floods and prunes back.
>
> Campus use case: AV-over-IP for lecture halls, digital signage, IPTV, or an IP-based paging/emergency notification system.

**45. What's the difference between NAC and SDP?**

> NAC (Cisco ISE, Aruba ClearPass) is the broader category 802.1X sits under — a policy engine deciding whether a device gets on the network at all and what it can reach, based on identity/posture. SDP, often called ZTNA, is the modern alternative to a traditional VPN — brokers access per-application rather than dropping a remote user onto the internal network, reducing blast radius if a device is compromised.
>
> On-campus: NAC/802.1X for access control. Remote access: SDP/ZTNA is the direction things are moving, even though VCA's current environment is still traditional VPN-based.

**46. What's the difference between RADIUS and TACACS+?**

> Both AAA protocols, different purposes. RADIUS combines authentication and authorization into one response, encrypts only the password field — built for network access AAA: wireless, VPN, 802.1X. TACACS+ separates authentication/authorization/accounting into distinct steps, encrypts the whole packet, Cisco's protocol of choice for device administration AAA.
>
> For campus infrastructure: TACACS+ is usually the answer to "how do you control admin access to network devices" — tie logins to a directory, enforce command-level authorization, get per-command accounting logs.

**47. Tell me about the campus cable plant — what standards and considerations matter?**

> The cable plant is the physical layer everything depends on — horizontal cabling from wiring closet to jack, backbone cabling between IDFs and the MDF. Horizontal runs: copper, Cat6/Cat6A, TIA/EIA-568 standards, 90-meter permanent-link limit. Backbone runs between buildings: fiber — multimode for shorter campus runs, singlemode where distance or future bandwidth justifies it.
>
> Good management means every run is labeled and documented at both ends, patch panels mapped to a system of record, and new runs certified with a cable tester before being trusted for production traffic.
>
> I do have hands-on experience here — patch cable termination, punch-down work, running and labeling cable, both in my home network and at the VCA corporate office. I use cable testers to verify RJ45 terminations end to end before trusting a run.

**48. Have you trained or supervised anyone?**

> I've supervised a part-time IT assistant at VCA — walked him through a new documentation system I set up alongside our Git-based change tracking, then tasked him with handling help desk requests directly. I check in with him and with the end user afterward to validate the work got done right.

**49. Tell me about a time you had to put together a cost analysis or proposal.**

> Most of my work at VCA is operational rather than budget-owning, but I have done comparative analysis — I put together a risk analysis comparing GitHub Teams versus GitLab for our source control decision, weighing cost, security posture, and migration effort before recommending a direction.

**50. How comfortable are you with Linux or Mac administration?**

> I've worked across all three. Linux for our Git server instances at work and in my own security homelabs — comfortable on the CLI. Mac for personal use and software development. Windows is my primary day-to-day at VCA, for both end-user and server administration.

**51. Are you available for off-hours work or a flexible schedule?**

> Yes — direct and honest affirmation, no hedging.

---

### Potential concerns

**52. You haven't actually administered Cisco in production.**

> That's accurate, and I'd rather be direct about it than oversell it. My production platforms have been HP Aruba and Fortinet. The CCNA is my direct response to that gap — it forces Cisco IOS fluency through structured curriculum and hands-on labs. The troubleshooting approach and the underlying protocols are the same regardless of vendor. I'd validate anything Cisco-specific in a lab before applying it to a live network here.

**53. Why are you leaving your current role? Why Whittier specifically?**

> A few things, honestly. The work at VCA has given me a solid foundation across networking, systems, and security — but the structure there is intentionally generalist. My director's goal is for me to cover all fronts, so I'm spread across endpoint management, identity, VoIP, and networking rather than going deep on any one of them. The networking is the part I want to specialize in, and this role is that opportunity: dedicated network ownership on a campus where the infrastructure actually drives the organization.
>
> The commute is also a real factor. I'm currently doing about two hours round trip. Whittier is under an hour from where I live. That's not a small thing — it means more energy for the actual work, and it means I'm more likely to be genuinely present rather than just grinding through the day.

**54. We've interviewed you twice. Why should this time be different?**

> Two things are materially different. The first is the CCNA — I'm completing it in August, which directly addresses the Cisco gap from the last interview. The second is that the scope at VCA has grown — I've been dealing with more complex network issues than I had when I interviewed last time, and I can speak to specific problems I've solved that I couldn't have talked about before.

**55. You've worked in enterprise/corporate settings, not education.**

> The infrastructure fundamentals are the same — VLANs, routing, PoE, wireless, security policy — but the stakeholder mix is different. A college has faculty, students, administration, and guests all on the same campus with different needs and different expectations for how IT communicates with them. I've had to calibrate communication differently depending on whether I'm talking to a VP, an end user, or a vendor, and I'd apply that same awareness here.

---

### Closing

**56. What questions do you have for me?**

1. "What does the network infrastructure look like today — how is it tiered, and what's the mix of hardware?"
2. "What did the previous person in this role do well, and where were the gaps they left?"
3. "The CCNA covers the concepts, but I'd be learning your specific environment on day one. What's the biggest technical gap you'd expect someone to need time to close?"
4. "How does the network team interact with the broader IT team here? Is this a solo network role or are there other people touching infrastructure?"
5. "What's the most urgent project or problem that needs attention in the first few months?"

Pick 3 in the moment based on what's already come up in conversation — don't ask something they've effectively already answered.
