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

The questions have escalated across both attempts. Round 1 was networking fundamentals. Round 2 went deep on Cisco specifics, campus design, and operational scenarios. Round 3 will likely continue that escalation — assume anything in the CCNA/CCNP space is fair game. Prepare answers you can say out loud, not just recognize on paper.

---

### OSI Model

Know every layer cold, with protocols at each one. They will ask this.

| Layer | Name | What it does | Key protocols |
|---|---|---|---|
| 7 | Application | User-facing services | HTTP, HTTPS, FTP, SMTP, DNS, SNMP |
| 6 | Presentation | Encoding, encryption, formatting | SSL/TLS, JPEG, ASCII |
| 5 | Session | Establish/maintain/terminate sessions | SSH, NetBIOS, RPC |
| 4 | Transport | End-to-end delivery, port numbers | TCP, UDP |
| 3 | Network | Logical addressing, routing | IP, ICMP, OSPF, BGP, EIGRP |
| 2 | Data Link | MAC addressing, framing, switching | Ethernet, 802.1Q, ARP, STP |
| 1 | Physical | Bits over wire | Cat5e/Cat6/fiber, hubs, repeaters |

**Likely follow-up:** "At which layer does a switch operate? A router?" Switch = Layer 2 (MAC); router = Layer 3 (IP). A Layer 3 switch does both.

---

### TCP vs. UDP

- **TCP:** connection-oriented, reliable, ordered. 3-way handshake: SYN → SYN-ACK → ACK. Used for HTTP, HTTPS, SSH, FTP, SMTP.
- **UDP:** connectionless, no handshake, no guaranteed delivery. Used where speed matters more than reliability: DNS, DHCP, VoIP (RTP), video streaming, SNMP.

**Why VoIP uses UDP:** a dropped packet in voice is less disruptive than the latency of retransmitting it. QoS compensates for the packet loss risk.

---

### ARP

Address Resolution Protocol maps an IP address to a MAC address. When a host needs to send to 10.0.0.5 but doesn't know its MAC, it broadcasts an ARP request ("who has 10.0.0.5?"). The owner replies with its MAC. The sender caches the result.

**Troubleshooting ARP issues:** `arp -a` on Windows/Linux to view ARP cache. ARP issues appear as "destination host unreachable" when the MAC can't be resolved. Common cause: wrong VLAN assignment — host on VLAN 10 trying to reach a host on VLAN 20 without a routed gateway.

**Gratuitous ARP:** a host announces its own IP/MAC mapping. HSRP/VRRP use this during failover so hosts update their ARP caches to point to the new active gateway.

---

### DNS

Resolution order: local cache → hosts file → configured DNS server → recursive lookup up the hierarchy (root → TLD → authoritative).

**`nslookup` / `dig`** for troubleshooting. If DNS is broken, users get "cannot resolve hostname" errors but can often ping by IP directly. Common campus issue: internal DNS not updated after IP changes.

---

### DHCP (DORA)

1. **Discover:** client broadcasts looking for a DHCP server
2. **Offer:** server responds with an available IP, subnet, gateway, DNS
3. **Request:** client formally requests the offered IP
4. **Acknowledge:** server confirms the lease

**DHCP relay (ip helper-address):** when DHCP server is on a different subnet/VLAN, configure `ip helper-address <DHCP server IP>` on the Layer 3 interface facing the client subnet. This forwards broadcasts to the DHCP server as unicast.

**Troubleshoot:** client not getting an IP — check helper-address on SVI, check DHCP pool has addresses, check VLAN assignment on port.

---

### Subnetting

Practice until you can calculate in your head:

- /24 = 256 addresses, 254 usable, mask 255.255.255.0
- /25 = 128 addresses, 126 usable, mask 255.255.255.128
- /26 = 64 addresses, 62 usable, mask 255.255.255.192
- /27 = 32 addresses, 30 usable, mask 255.255.255.224
- /28 = 16 addresses, 14 usable, mask 255.255.255.240
- /30 = 4 addresses, 2 usable — used for point-to-point links

**Formula:** usable hosts = 2^(32-prefix) - 2

**Likely exam question:** "You have 10.10.10.0/24. Divide it into 4 equal subnets." Answer: /26 gives 4 subnets of 64 addresses each: .0, .64, .128, .192.

---

### VLANs and Trunking

VLANs segment Layer 2 broadcast domains logically. Traffic stays within a VLAN unless routed.

**802.1Q tagging:** a 4-byte tag inserted into the Ethernet frame header containing the VLAN ID (12 bits = 4094 max VLANs) and priority bits (used for QoS).

- **Access port:** single VLAN, untagged. For end devices (PCs, printers, phones).
- **Trunk port:** carries multiple VLANs, tagged. Between switches and to routers.
- **Native VLAN:** traffic on the native VLAN is untagged on a trunk. Mismatch is a security risk (VLAN hopping); set native VLAN to an unused VLAN ID.

**Inter-VLAN routing options:**
1. Layer 3 switch with SVIs: `interface vlan 10` → `ip address 10.0.10.1 255.255.255.0` → `no shutdown`. Preferred for performance.
2. Router-on-a-stick: one trunk to router, subinterfaces per VLAN (`interface g0/0.10` → `encapsulation dot1q 10` → `ip address`). Simpler but bandwidth-limited.

**Key IOS commands:**
```
show vlan brief                          # VLAN assignments
show interfaces trunk                    # trunk ports and allowed VLANs
switchport mode access
switchport access vlan 10
switchport mode trunk
switchport trunk allowed vlan 10,20,30
switchport voice vlan 20                 # for IP phone ports
```

---

### Cisco IOS Essentials

**Show commands — know these cold:**
```
show ip interface brief       # all interfaces: IP, status, protocol
show interfaces gi0/0         # detailed stats: errors, drops, utilization
show running-config           # current config
show startup-config           # saved config
show version                  # IOS version, uptime, hardware
show ip route                 # routing table
show vlan brief               # VLAN table
show interfaces trunk         # trunk summary
show spanning-tree            # STP topology per VLAN
show cdp neighbors detail     # connected Cisco devices with IPs
show lldp neighbors           # connected devices (open standard)
show ip ospf neighbor         # OSPF adjacency states
show ip eigrp neighbors       # EIGRP neighbor table
show ip bgp summary           # BGP session states
show mac address-table        # MAC to port mappings
```

**Config mode flow:**
```
enable
configure terminal
interface GigabitEthernet0/1
  ip address 192.168.1.1 255.255.255.0
  no shutdown
exit
```

**Save config:**
```
copy running-config startup-config    # or: write memory
```

---

### Spanning Tree Protocol (STP / RSTP)

STP prevents Layer 2 loops by blocking redundant paths. Without it, broadcast storms bring down the network.

**Root bridge election:** lowest bridge priority (default 32768) wins. Tie broken by lowest MAC. Set core/distribution switches as root: `spanning-tree vlan 1 priority 0`.

**Port roles:** Root (best path to root bridge), Designated (best on each segment), Alternate (blocked backup).

**STP port states:** Blocking → Listening → Learning → Forwarding (slow, ~50 seconds)

**RSTP (802.1w):** faster convergence (~1 second). States: Discarding → Learning → Forwarding. Use on all modern networks.

```
spanning-tree mode rapid-pvst         # enable RSTP (per-VLAN)
spanning-tree portfast                # skip Listening/Learning on access ports
spanning-tree bpduguard enable        # shut port if BPDU received (rogue switch protection)
```

**Likely question:** "The network is experiencing a broadcast storm. What's your first thought?" Check for STP loop — a newly added switch or a portfast port receiving BPDUs. Check `show spanning-tree` for ports in inconsistent state.

---

### OSPF

Link-state protocol. Each router builds a complete map of the network (LSDB) and runs Dijkstra's algorithm (SPF) to find shortest paths.

**Adjacency requirements:** same area, same Hello/Dead timers, same subnet, same network type, authentication if configured. On broadcast networks (Ethernet), a Designated Router (DR) is elected — highest priority (default 1), then highest router-id.

**Adjacency states:** Down → Init → 2-Way → ExStart → Exchange → Loading → Full

**Troubleshoot "OSPF neighbors not forming":**
1. `show ip ospf neighbor` — no entry means packets not reaching neighbor
2. Check interface is in OSPF: `show ip ospf interface`
3. Check Hello/Dead timers match: `show ip ospf interface gi0/0`
4. Check same area ID on both sides
5. Check no passive interface set: `show run | include passive`
6. Check network type matches (point-to-point vs broadcast)
7. Check ACL not blocking multicast 224.0.0.5/224.0.0.6

```
router ospf 1
  network 10.0.0.0 0.255.255.255 area 0
show ip ospf neighbor
show ip ospf database
```

---

### EIGRP

Cisco-proprietary (now also on non-Cisco). Uses DUAL algorithm. Composite metric based on bandwidth and delay (by default).

- **Successor:** best route (lowest feasible distance) in routing table
- **Feasible successor:** backup route in topology table satisfying the feasibility condition (reported distance < feasible distance of successor). If successor fails, feasible successor promotes instantly — no recalculation.

```
show ip eigrp neighbors
show ip eigrp topology          # all routes including feasible successors
```

**Likely question:** "What's the difference between OSPF and EIGRP?" OSPF is open standard, link-state, uses SPF. EIGRP is Cisco-proprietary, hybrid (distance-vector with fast convergence), uses DUAL. OSPF scales better in large networks; EIGRP is simpler to configure in small/medium Cisco environments.

---

### BGP

Used between autonomous systems (eBGP) or within AS (iBGP). For a campus like Whittier College, BGP would appear for ISP peering (multi-homed or failover to a second ISP).

- eBGP: between different AS numbers. Usually directly connected peers.
- iBGP: within same AS. Requires full mesh or route reflectors.
- BGP is policy-driven, not metric-driven.

**Honest framing:** "I understand BGP conceptually from CCNA studies. At VCA we're dual-ISP (AT&T fiber primary, Spectrum failover), but that failover runs through the Fortinet's SD-WAN rather than BGP, so I haven't administered a BGP session in production. For a campus setup where BGP is genuinely in play, I'd be comfortable building from documentation and testing in a lab before any cutover."

```
show ip bgp summary             # BGP neighbor states (Established = healthy)
```

---

### HSRP / VRRP

First-hop redundancy — provides a virtual gateway IP shared between two routers/L3 switches. If the active device fails, standby takes over using the same virtual IP, so end devices don't need to update their default gateway.

- **HSRP** (Cisco): Active/Standby model. Virtual IP and virtual MAC. Higher priority = active.
- **VRRP** (open standard): Master/Backup. Virtual IP can match the master's real IP.

**Campus use case:** two distribution switches, each connected to core. HSRP gives access layer a consistent gateway. Preempt ensures the higher-priority switch reclaims active after recovery.

```
interface vlan 10
  standby version 2
  standby 1 ip 10.0.10.254
  standby 1 priority 110
  standby 1 preempt
```

---

### QoS and IP Phone Systems

VoIP requirements: latency under 150ms one-way, jitter under 30ms, packet loss under 1%. Without QoS, voice and bulk data compete equally for bandwidth.

**DSCP marking:**
- EF (Expedited Forwarding, DSCP 46): voice RTP traffic — strict priority queue
- AF41 (DSCP 34): video conferencing
- CS0 (Best Effort): general traffic

**Classification and marking:** identify traffic at the edge (by port, protocol, or DSCP marking from the phone), mark it, then apply queuing policy.

**LLQ (Low Latency Queuing):** reserves bandwidth for voice with a strict priority queue — voice packets are always served first up to the reserved bandwidth.

**IP phone integration on a Cisco switch:**
- Phone connects to access port
- Switch uses CDP (or LLDP) to tell phone which voice VLAN to use
- Phone gets IP from DHCP in the voice VLAN; PC connects through phone and gets IP from data VLAN
- Switch port config for phone + PC:

```
switchport mode access
switchport access vlan 10          # data VLAN for PC
switchport voice vlan 20           # voice VLAN for phone
spanning-tree portfast             # no delay for phone coming online
mls qos trust cos                  # trust CoS marking from phone
```

**LLDP vs CDP:** CDP is Cisco-proprietary and the default for phone discovery on Cisco switches. LLDP (IEEE 802.1AB) is the open standard equivalent. LLDP-MED extends it for VoIP. This is why the LLDP misconfiguration at VCA blocked one-touch provisioning — the switch wasn't advertising the voice VLAN via LLDP to the phones.

---

### Campus Network Design (comprehensive)

**Three-tier model:**
- **Core:** high-speed backbone, Layer 3 only, no end devices. Fast switching, redundant links. Cisco Catalyst 9500/9400.
- **Distribution:** inter-VLAN routing, ACLs, QoS policies, HSRP. Aggregates access layer uplinks.
- **Access:** end device connections, PoE for phones and APs, VLAN assignment, portfast/bpduguard.

**Two-tier (collapsed core):** Distribution and Core combined. Common in smaller campuses like Whittier. Two distribution switches in a redundant pair (HSRP), each connected to all access switches.

**For Whittier College specifically:**
- Likely two-tier with redundant distribution/core switches
- Access switches in each building uplinked to distribution via fiber (multi-mode or single-mode depending on distance)
- VLANs: Staff, Faculty, Student, VoIP, IoT, Management, Guest
- Wireless: SSIDs mapped to VLANs via trunk to wireless controller or APs
- Routing: OSPF internally between distribution and any routers; static or BGP to ISP

**Likely interview question:** "Walk me through how you'd implement a campus network."

Answer framework:
1. Assess requirements: number of users, buildings, VoIP, wireless, bandwidth needs
2. Design VLANs and IP addressing scheme (don't overlap, document everything)
3. Choose hardware: core/distribution switches, access switches with appropriate PoE budget
4. Cable plant: fiber between buildings, copper Cat6A within buildings to wall plates
5. Configure spanning tree (RSTP), root bridge on distribution
6. Configure inter-VLAN routing (SVIs on distribution)
7. Configure DHCP (either on switches or centralized server with ip helper-address)
8. Configure HSRP on distribution for gateway redundancy
9. Add wireless (WLCs or cloud-managed APs), trunk SSIDs to VLANs
10. Configure QoS for VoIP
11. Implement security: 802.1X where applicable, ACLs between VLANs, management VLAN isolated
12. Document topology, IP addressing, VLAN table, firewall rules

---

### Ethernet Cable Categories

| Category | Max speed | Max distance | Bandwidth | Notes |
|---|---|---|---|---|
| Cat5 | 100 Mbps | 100m | 100 MHz | Obsolete |
| Cat5e | 1 Gbps | 100m | 100 MHz | Reduced crosstalk; still common |
| Cat6 | 10 Gbps (55m) / 1 Gbps (100m) | 100m | 250 MHz | Thicker, stiffer; good for most deployments |
| Cat6A | 10 Gbps | 100m | 500 MHz | Current standard for new runs; handles PoE++ heat better |
| Cat7 | 10 Gbps | 100m | 600 MHz | Shielded (STP); not TIA-recognized; rarely used |
| Cat8 | 25/40 Gbps | 30m | 2 GHz | Data center use only |

**Practical takeaway:** new campus cable plant runs should be Cat6A minimum. Existing Cat5e supports 1G endpoints fine. Cat6A handles 10G and better thermal performance under high PoE loads.

---

### Router/Switch Upgrade Process

1. **Pre-work:** `show version` to confirm current IOS version; `show running-config` and save a backup copy externally
2. **Download image:** get correct IOS-XE or IOS image from Cisco for your hardware; verify MD5/SHA hash
3. **Copy to flash:** `copy tftp: flash:` (enter TFTP server IP and filename) or via SCP
4. **Verify:** `dir flash:` — confirm image present and correct size
5. **Set boot variable:** `boot system flash:/<new-image>.bin`
6. **Save config:** `copy running-config startup-config`
7. **Schedule maintenance window** (off-hours; notify stakeholders)
8. **Reload:** `reload` — confirm prompt
9. **Post-upgrade verification:** `show version`, ping tests, check `show ip ospf neighbor`, check VLANs, check logs for errors
10. **Rollback plan:** if bad — boot to previous image (set boot system back to old image), or use `software install rollback` on IOS-XE install mode

**IOS-XE install mode** (newer devices): supports In-Service Software Upgrade (ISSU) on stacked/modular hardware for hitless upgrades.

---

### Config Backup Process

**Manual (IOS):**
```
copy running-config tftp:            # enter TFTP server IP and filename
copy running-config scp:             # preferred (encrypted)
```

**Automated (recommended for campus):**
- **Oxidized or RANCID:** open-source tools that SSH into devices on a schedule, pull running-config, and commit to a Git repo. Gives full version history and diffs when configs change.
- **Git-backed storage:** each device gets its own file; changes are visible as diffs. Already do this at VCA with DEM configs — same principle.
- **Backup frequency:** at minimum, run on a schedule (daily or after change windows). Trigger backup after any config change.
- **What to back up:** running-config, startup-config, and for firewalls, the full policy export.

**Answer for interview:** "I'd set up Oxidized to pull configs on a schedule and push them to a Git repository. Every config change shows up as a commit with a diff, which also doubles as an audit trail. I already use this approach for version-controlling infrastructure configs at VCA."

---

### Troubleshooting Methodology

**Bottom-up (most systematic):**
1. Physical: cable connected? Interface up? `show interfaces` — check for errors, CRC, input/output drops
2. Data Link: correct VLAN? `show mac address-table`, `show interfaces trunk`
3. Network: correct IP, subnet, gateway? `show ip route` — is the route present?
4. Transport: port reachable? `telnet <ip> <port>` or `nc` to test port connectivity
5. Application: service running? DNS resolving?

**Key tools:**
- `ping` — basic reachability
- `traceroute` — path and where it breaks
- `show interfaces <int>` — input/output errors indicate physical or duplex issues
- `debug ip packet` — use carefully in production; generates a lot of output
- `show log` — recent syslog messages on device
- SNMP/NMS (SolarWinds, LibreNMS, PRTG) for historical performance data
- Wireshark/packet capture for application-layer issues

---

### Network Documentation (Day 1 at Whittier)

Answer for "how would you approach documenting the existing network when you start?":

1. Run `show cdp neighbors detail` / `show lldp neighbors detail` on core/distribution to map connected devices and IPs
2. Export routing tables: `show ip route` on each L3 device
3. Export VLAN tables: `show vlan brief` on each switch
4. SNMP walk or NMS scan (LibreNMS/PRTG) to auto-discover all devices
5. Pull all configs via SCP and put them in a Git repo (set up Oxidized)
6. Draw physical topology (buildings, fiber runs, patch panels) and logical topology (VLANs, routing, WAN)
7. Build IP address management spreadsheet or IPAM tool
8. Review firewall rules and NAT policies
9. Interview current/departing admin if possible — ask about known issues, pending projects, maintenance schedules

---

### Your Honest Framing for Cisco Gaps

When asked about Cisco IOS or routing protocol operational experience:

> "My hands-on platforms have been Fortinet and HP Aruba, so I've built the operational instincts there. I've been building Cisco IOS fluency through CCNA Packet Tracer labs — the CLI syntax is different but the underlying concepts are the same. I'm completing the CCNA in August, which covers OSPF, EIGRP, trunking, and ACL configuration. For anything I haven't touched in production, I'd validate in a lab environment before applying to a live network."

When asked about BGP specifically:

> "I understand BGP at the conceptual level — AS numbers, eBGP vs. iBGP, path selection. I haven't administered a BGP session in production. For a dual-ISP campus setup, I'd work from documentation and test the config thoroughly before any cutover."

The line that matters: be specific about what you know, specific about what you don't, and specific about how you'd close the gap. Vague confidence is worse than honest acknowledgment.

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

| Metric            | Target                | Actual |
| ----------------- | --------------------- | ------ |
| Submission date   | ASAP                  |        |
| Follow-up sent    | Day 7 post-submission |        |
| Response received |                       |        |
| Interview date    |                       |        |
| Offer / rejection |                       |        |

---

_Generated using Career Helper skill by Paul Bratcher ([LinkedIn](https://www.linkedin.com/in/paul-bratcher/) | [GitHub](https://github.com/Zal4DW/career-helper)). Found this helpful? Share your success story or suggest improvements on GitHub!_
