# Subnetting / VLSM Answer Key

Answers to `subnetting-vlsm-exercises.md`. Don't peek until you've worked the problem.

---

## Section A

1. Need 6 subnets → borrow 3 bits (2³=8 ≥ 6) → `/27` (255.255.255.224). 8 subnets, 30 usable hosts each.
2. Need ≥50 hosts → 2⁶-2=62 ≥ 50, 2⁵-2=30 <50 → need 6 host bits → `/26` (255.255.255.192), 62 usable hosts.
3. 500 subnets needs 9 bits (2⁹=512) → `/17`, leaving 15 host bits = 32,766 hosts/subnet — technically satisfies "at least 100 hosts" easily, but wastes massive address space. This is exactly the case VLSM exists to avoid.
4. `/30` (255.255.255.252) — 2 usable hosts, zero waste. (Note: some shops now use `/31` for point-to-point per RFC 3021, worth mentioning if asked.)
5. Need 30 subnets → 2⁵=32 ≥30 → borrow 5 bits → `/29` (255.255.255.248), 6 usable hosts per subnet.

## Section B

6. `172.20.14.130/27` → block size 32 → network `172.20.14.128`, broadcast `.159`, range `.129–.158`, 30 hosts.
7. `10.55.200.6/22` → block size 4 in 3rd octet → network `10.55.200.0`, broadcast `10.55.203.255`, range `10.55.200.1–10.55.203.254`, 1022 hosts.
8. `192.168.100.191/26` → block size 64 → network `.128`, broadcast `.191`, range `.129–.190`, 62 hosts.
9. `172.16.90.45/20` → block size 16 in 3rd octet → network `172.16.80.0`, broadcast `172.16.95.255`, range `172.16.80.1–172.16.95.254`, 4094 hosts.
10. `10.10.10.10/30` → block size 4 → network `.8`, broadcast `.11`, range `.9–.10`, 2 hosts.
11. `192.168.1.75/28` → block size 16 → network `.64`, broadcast `.79`, range `.65–.78`, 14 hosts.

## Section C

12. `/21` = block size 8 in 3rd octet → boundaries at 16, 24. `.16.55` is in `10.1.16.0/21`; `.20.10` is also in `10.1.16.0/21` (range 16–23). **Same subnet.**
13. `/27` = block size 32 → boundaries at 32, 64, 96. `.60` is in `192.168.5.32/27` (32–63); `.90` is in `192.168.5.64/27` (64–95). **Different subnets.**
14. `/18` (255.255.192.0) → block size 64 in 2nd octet → `172.16.192.0/18`, range `172.16.192.1–172.16.255.254`.

## Section D

15. Largest-first allocation from `192.168.20.0/24`:
    - Student lab (100 hosts, needs /25=126) → `192.168.20.0/25`, range `.1–.126`, broadcast `.127`
    - Staff (50 hosts, needs /26=62) → `192.168.20.128/26`, range `.129–.190`, broadcast `.191`
    - Guest (20 hosts, needs /27=30) → `192.168.20.192/27`, range `.193–.222`, broadcast `.223`
    - Printers/IoT (10 hosts, needs /28=14) → `192.168.20.224/28`, range `.225–.238`, broadcast `.239`
    - P2P link 1 (/30) → `192.168.20.240/30`, range `.241–.242`, broadcast `.243`
    - P2P link 2 (/30) → `192.168.20.244/30`, range `.245–.246`, broadcast `.247`
    - (`.248–.255` left unused/reserved for growth)

16. From `10.10.0.0/16`:
    - Building A (400 hosts, needs /23=510) → `10.10.0.0/23`, range `10.10.0.1–10.10.1.254`, broadcast `10.10.1.255`
    - Building B (200 hosts, needs /24=254) → `10.10.2.0/24`, range `10.10.2.1–10.10.2.254`, broadcast `10.10.2.255`
    - Building C (60 hosts, needs /26=62) → `10.10.3.0/26`, range `10.10.3.1–10.10.3.62`, broadcast `10.10.3.63`
    - P2P links (/30 each) → `10.10.3.64/30`, `10.10.3.68/30`, `10.10.3.72/30`

## Section E

17. `255.255.255.192` → wildcard = `0.0.0.63` (255 - each octet).
18. `172.16.4.0 0.0.3.255` (a /22 has block size 4 in 3rd octet → wildcard covers 4 in that octet: `0.0.3.255`, then `.255` in last octet).
19. `0.0.0.63` = a block size of 64 → matches a `/26` subnet.
