# Subnetting / VLSM Drilling Exercises

CCNA-style practice set. Work each problem cold, then check against `subnetting-vlsm-answer-key.md`. Time yourself — fluency means solving these in well under a minute each.

---

## Section A: Basic subnetting (given requirements, find the mask)

1. You need 6 subnets from **192.168.10.0/24**. What subnet mask do you use, how many subnets does it actually give you, and how many usable hosts per subnet?
2. You need at least 50 usable hosts per subnet from **172.16.0.0/16**. What's the smallest mask that satisfies this, and how many usable hosts does it give you?
3. You need to subnet **10.0.0.0/8** to support 500 subnets, each with at least 100 hosts. Is this possible without VLSM? Show your work.
4. A network needs point-to-point WAN links between routers. What mask minimizes wasted addresses for a link that only ever has 2 hosts?
5. Given **200.10.5.0/24**, you need 30 subnets. What mask do you use, and how many hosts are usable per subnet?

## Section B: Given IP + mask, identify the subnet details

For each, find: network address, broadcast address, first usable host, last usable host, and total usable hosts.

6. `172.20.14.130/27`
7. `10.55.200.6/22`
8. `192.168.100.191/26`
9. `172.16.90.45/20`
10. `10.10.10.10/30`
11. `192.168.1.75/28`

## Section C: "Which subnet is this host on / are these two hosts on the same subnet?"

12. Are `10.1.16.55/21` and `10.1.20.10/21` on the same subnet?
13. Are `192.168.5.60/27` and `192.168.5.90/27` on the same subnet?
14. A host has IP `172.16.202.10` with mask `255.255.192.0`. What subnet is it on, and what's the valid host range?

## Section D: VLSM design (campus-relevant — multi-VLAN scenario)

15. You're given **192.168.20.0/24** to design for a small campus building with these needs:
    - Staff VLAN: 50 hosts
    - Student lab VLAN: 100 hosts
    - Guest Wi-Fi VLAN: 20 hosts
    - Printers/IoT VLAN: 10 hosts
    - 2 point-to-point router links between distribution switches

    Allocate VLSM subnets for each, starting from the largest requirement first. Give the subnet, mask, usable range, and broadcast address for each.

16. You're given **10.10.0.0/16** for a larger site with:
    - Building A: 400 hosts
    - Building B: 200 hosts
    - Building C: 60 hosts
    - 3 point-to-point WAN links

    Design the VLSM allocation, largest to smallest, most efficient use of address space.

## Section E: Wildcard masks (ACL-relevant)

17. Convert `255.255.255.192` to a wildcard mask.
18. You want an ACL to match only the subnet `172.16.4.0/22`. What network + wildcard mask do you write in the ACL line?
19. What does wildcard mask `0.0.0.63` tell you about the subnet size it's matching?
