# COIT13236 Cyber Security Project — Melbourne Metro Health Network (MMHN)

**Central Queensland University | HT1 2026 | Topic 7: Healthcare Network Design**

---

## Project Overview

This project designs and prototypes a secure multi-campus network for the **Melbourne Metro Health Network (MMHN)** a fictional healthcare organisation operating across three sites in Melbourne: Clayton (primary hospital), Mernda (community health), and CBD (administration and specialists).

The goal was to go from zero to a working, documented network design that meets Australian healthcare compliance requirements, with a physical prototype to back it up.

The design applies a **hub-and-spoke topology** with a centralised cloud hub at CBD, VLAN-based traffic segmentation, IPSec VPN tunnels for inter-campus communication, and layered perimeter security using Cisco ASA firewalls.

---

## Team

| Role | Member | Responsibilities |
|------|--------|-----------------|
| Project Manager | Ashikha Pakkiru | Timeline, coordination, final submission |
| Network Design Lead | Kunj Patel | Logical topology, VLAN structure, cloud connectivity |
| Security Specialist | Kunj Acharya | Firewall rules, VPN architecture, compliance mapping |
| Prototype & Testing Lead | Masum Patel | Packet Tracer build, physical lab prototype, test results |

---

## Network Design

### Topology

Hub-and-spoke design. CBD campus is the hub. Clayton and Mernda are spokes. All inter-campus traffic routes through the CBD hub via IPSec VPN tunnels over the public internet.

```
Internet
    |
  ISP Router
    |
Central Firewall (Cisco ASA 5506-X) — CBD
    |
CBD Core Switch (Catalyst 3560, L3)
    |------ CBD Campus LAN
    |------ Clayton Campus (via IPSec VPN tunnel)
    |------ Mernda Campus (via IPSec VPN tunnel)
```

### Devices

| Device | Model | Role |
|--------|-------|------|
| Campus routers | Cisco 2911 | Campus gateway + IPSec VPN termination |
| CBD core switch | Cisco Catalyst 3560 (L3) | Inter-VLAN routing at CBD |
| Branch switches | Cisco 2960 (L2) | Access layer at Clayton and Mernda |
| Firewall | Cisco ASA 5506-X | Perimeter security, DMZ, stateful inspection |
| Wireless controller | WLC-PT | Centralised AP management |
| Access points | AP-PT (2 per campus) | Wireless access |
| Servers | Server-PT x3 | Patient data, authentication, backup |

### VLANs (per campus)

| VLAN ID | Name | Purpose |
|---------|------|---------|
| 10 | Admin | Administrative staff |
| 20 | Doctor-Clinical | Clinical staff and patient systems |
| 30 | IoT-Medical | Patient monitors, infusion pumps, sensors |
| 40 | Guest-WiFi | Visitor wireless access |

### IP Addressing Scheme

**WAN links (ISP to campus routers):**
- ISP to CBD: `203.0.113.0/30`
- ISP to Clayton: `203.0.113.4/30`
- ISP to Mernda: `203.0.113.8/30`

**Campus LAN subnets:**

| Campus | Admin | Clinical | IoT | Guest |
|--------|-------|----------|-----|-------|
| CBD | 192.168.10.0/24 | 192.168.20.0/24 | 192.168.30.0/24 | 192.168.40.0/24 |
| Clayton | 192.168.11.0/24 | 192.168.21.0/24 | 192.168.31.0/24 | 192.168.41.0/24 |
| Mernda | 192.168.12.0/24 | 192.168.22.0/24 | 192.168.32.0/24 | 192.168.42.0/24 |

**CBD servers (DMZ):**
- `CBD-DATA-01` (patient data): `172.16.1.10/24`
- `CBD-AUTH-01` (authentication): `172.16.0.20/24`
- `CBD-BACKUP-01` (backup/redundancy): `172.16.2.20/24`

### Security Design

**Firewall (Cisco ASA 5506-X at CBD):**
- Four security zones: `outside (level 0)`, `dmz-auth (level 50)`, `dmz-data (level 50)`, `inside (level 100)`
- Stateful inspection on all inbound/outbound traffic
- ACL rules applied per zone

**VPN:**
- Protocol: IPSec IKEv1
- Encryption: AES-256
- Hash: SHA
- Auth: Pre-shared key
- DH group: 2 | Lifetime: 86400s
- Transform set: ESP-AES-256 + ESP-SHA-HMAC

**ACL rules (enforced on all campuses):**
- Guest → Admin: **DENY**
- Guest → Clinical: **DENY**
- Guest → IoT: **DENY**
- IoT → Clinical: **DENY**
- IoT → Guest: **DENY**
- Clinical → Guest: **DENY**

**Wireless:**
- WPA2 on all access points
- Guest VLAN isolated from internal traffic

**VLAN segmentation method:**
- Layer 2: 802.1Q tagging on trunk links, access ports per VLAN
- Layer 3: ACLs on router sub-interfaces (Clayton, Mernda) and SVIs (CBD 3560)
- Perimeter: ASA stateful inspection at CBD

---

## Repository Structure

```
Cyber-security-Project--main/
│
├── README.md
│
└── Journal/
    ├── Week1-3.md    — Project setup, topic selection, proposal submission
    ├── Week4.md      — Network design document, topology, device details
    ├── Week5.md      — First diagram iteration, Packet Tracer start, mentor feedback
    ├── Week6.md      — Design locked in, Packet Tracer near-complete, progress report
    ├── Week7.md      — Redesign after mentor feedback, draw.io diagrams, design finalised
    ├── Week8.md      — Full Packet Tracer simulation: VLANs, ACLs, VPN, firewall, testing
    ├── week9.md      — Physical prototype begins in university lab
    ├── Week10        — Physical lab: IP config, file sharing, connectivity testing
    ├── Week 11.md    — Physical prototype goals: VLANs, security, routing, video evidence
    └── Week-12.md    — Physical prototype: CBD + Clayton IPs assigned and verified
```

---

## Weekly Progress Summary

| Week | Key Milestone |
|------|--------------|
| 1–3 | Team formed, roles assigned, proposal submitted |
| 4 | Network design document completed with topology, VLANs, data flow |
| 5 | First Packet Tracer build, initial diagram, mentor feedback received |
| 6 | Design revision locked in, all IPs assigned, Packet Tracer near-complete |
| 7 | Full redesign after mentor feedback, draw.io diagram finalised (Design 1 & 2) |
| 8 | Complete Packet Tracer simulation — VLANs, ACLs, VPN, firewall, all tests passed |
| 9 | Physical prototype started in lab — router → switch → laptop connectivity verified |
| 10 | Lab session: IP config, ping tests, file sharing, network profile troubleshooting |
| 11 | Physical prototype goals set: VLAN config, security hardening, routing |
| 12 | CBD (192.168.10.1) and Clayton (192.168.11.1) routers configured and verified |

---

## Simulation Results (Packet Tracer)

All tests conducted in Cisco Packet Tracer 8.2.2.

| Test | Result |
|------|--------|
| Clayton Admin → Mernda Admin | PASS |
| Clayton Admin → CBD Admin | PASS |
| Mernda Admin → CBD Admin | PASS |
| Clayton Doctor → Mernda Doctor | PASS |
| Guest Phone → Admin PC (same campus) | FAIL (ACL working correctly) |
| Clayton–CBD VPN (QM_IDLE) | ACTIVE |
| Mernda–CBD VPN (QM_IDLE) | ACTIVE |
| Clayton–Mernda VPN (QM_IDLE) | ACTIVE |

---

## Physical Prototype Results

| Test | Result |
|------|--------|
| Laptop → CBD router (192.168.10.1) ping | PASS — 0% packet loss |
| PC → Clayton router (192.168.11.1) ping | PASS |
| Mernda router IP assignment | Pending |
| Switch VLAN configuration | Pending (console driver issue) |
| Inter-campus routing | Pending |

---

## Notable Technical Decisions

**ASA 5506-X over 5505** — The 5505 Base license only allows 2 named interfaces in Packet Tracer, which blocked DMZ creation. Replaced with 5506-X (Security Plus license, unlimited interfaces).

**ISP router instead of Cloud-PT** — Cloud-PT requires manual internal port mapping to pass traffic. The standard Packet Tracer approach of using an ISP router as the internet was used instead.

**Static IPs over DHCP** — The ASA firewall blocks DHCP relay broadcasts between security zones. All end devices assigned static IPs for reliable connectivity.

**No campus firewalls at Clayton/Mernda** — The ASA 5506-X does not support VLAN sub-interfaces on physical ports in Packet Tracer simulation. Clayton and Mernda rely on VPN encryption and router ACLs. CBD handles all DMZ and perimeter security.

**Backup server added** — Following tutor feedback on single-point-of-failure risk, `CBD-BACKUP-01` was added to replicate patient records and the authentication database.

---

## Known Limitations / Future Improvements

- Clayton and Mernda should have dedicated next-gen firewalls (e.g. Cisco Firepower) in a production environment
- DHCP server in the DMZ with `ip helper-address` on campus routers would remove static IP requirement
- CBD-FW-01 is a single point of failure — Active/Standby HA pair should be implemented in production
- WLC was placed but not fully integrated — production setup would centrally manage all APs across all campuses
- CBD-BACKUP-01 is on the inside network due to Packet Tracer limitations — should sit in a dedicated DMZ zone in production

---

## Tools Used

| Tool | Purpose |
|------|---------|
| Cisco Packet Tracer 8.2.2 | Network simulation and testing |
| draw.io | Logical network diagrams |
| GitHub | Version control and evidence tracking |
| Microsoft Word | Report writing and documentation |
| Physical lab (Cisco 3560-CX, TP-Link routers, UniFi AP) | Physical prototype |

---

## Compliance References

This design was built to align with the following:

- Australian Privacy Act 1988
- My Health Records Act 2012
- Australian Cyber Security Centre — Information Security Manual (ISM) 2022
- ISO/IEC 27001:2013

---

## Methodology

Design follows **Oppenheimer's Top-Down Network Design** methodology — requirements drive design, design drives prototype, prototype validates the documentation.

---

*COIT13236 Cyber Security Project — HT1 2026 — Central Queensland University*
