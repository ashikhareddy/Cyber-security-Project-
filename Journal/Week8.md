# Week 08 - Network Simulation Log

COIT13236 | Melbourne Metro Health Network (MMHN)
HT1 2026 | Central Queensland University

Team: Ashikha Pakkiru, Kunj Patel, Kunj Acharya, Masum Patel

---

## What we did this week

This week the group focused entirely on building the MMHN network in Cisco Packet Tracer. The goal was to take the logical design from earlier weeks and turn it into a working simulation. We configured VLANs, inter-campus routing, wireless, access control, firewall zones, and IPSec VPN tunnels across all three campuses.

---
## Network Design Final

<img width="1915" height="1621" alt="Networkdesignfinal drawio" src="https://github.com/user-attachments/assets/25ee0967-1c1b-41fc-a098-76806005c8f4" />

[Uploading NetworkDesign.drawio…]()

## Device setup

We confirmed the following devices were available in Packet Tracer 8.2.2 and placed them on the canvas:

- 4x Cisco 2911 routers (ISP, CBD, Clayton, Mernda)
- 1x Cisco Catalyst 3560-24PS (CBD core switch, Layer 3)
- 2x Cisco 2960 (Clayton and Mernda access switches, Layer 2)
- 1x Cisco ASA 5506-X (CBD firewall)
- 1x WLC-PT (wireless LAN controller at CBD)
- 6x AP-PT (2 per campus)
- 2x Server-PT (CBD-DATA-01 and CBD-AUTH-01)
- End devices: PCs, laptops, tablets, smartphones, printers

All devices were labelled using a consistent naming format, for example CLAY-RTR-01, CLAY-SW-01, CBD-FW-01, and so on.

---

## Cabling

All devices were connected using the Automatic cable option in Packet Tracer. Switch uplinks to routers were set as trunk ports carrying VLANs 10, 20, 30 and 40. Access point ports were set as access ports on the appropriate VLAN.

We initially tried using the Cloud-PT device to represent the internet between campuses. After testing we found that Cloud-PT does not route traffic between connected devices without manual internal port mapping, which was not practical for our setup. We removed the cloud and connected all campus routers directly to the ISP router instead. The ISP router acts as the internet in the simulation, which is the standard Packet Tracer approach.

---

## IP addressing

WAN links between ISP and campus routers use /30 subnets.

- ISP to CBD: 203.0.113.0/30
- ISP to Clayton: 203.0.113.4/30
- ISP to Mernda: 203.0.113.8/30

Campus LAN subnets by VLAN:

- CBD Admin: 192.168.10.0/24
- CBD Doctor: 192.168.20.0/24
- CBD IoT: 192.168.30.0/24
- CBD Guest: 192.168.40.0/24
- Clayton Admin: 192.168.11.0/24
- Clayton Doctor: 192.168.21.0/24
- Clayton IoT: 192.168.31.0/24
- Clayton Guest: 192.168.41.0/24
- Mernda Admin: 192.168.12.0/24
- Mernda Doctor: 192.168.22.0/24
- Mernda IoT: 192.168.32.0/24
- Mernda Guest: 192.168.42.0/24

DMZ servers at CBD:

- CBD-DATA-01 (patient data storage): 172.16.1.10/24
- CBD-AUTH-01 (authentication server): 172.16.0.20/24

All end devices were assigned static IPs. DHCP was attempted but could not be made to work reliably because the ASA firewall blocks DHCP relay broadcasts between zones. Static addressing was more practical for the simulation.

---

## VLANs

Four VLANs were configured on all campus switches:

- VLAN 10: Admin
- VLAN 20: Doctor-Clinical
- VLAN 30: IoT-Medical
- VLAN 40: Guest-WiFi

The CBD core switch (3560) handles inter-VLAN routing using the ip routing command since it is a Layer 3 switch. Clayton and Mernda use router-on-a-stick because their 2960 switches are Layer 2 only. Sub-interfaces were created on each campus router for each VLAN.

---

## Firewall

We originally planned to use the ASA 5505 at each campus. During configuration we hit a hard licensing wall on the 5505.

Error received:
```
ERROR: This license does not allow configuring more than 2 interfaces
with nameif and without a no forward command
```

The ASA 5505 Base license in Packet Tracer only allows 2 named interfaces, which meant we could not create a DMZ zone. We replaced all firewall devices with the ASA 5506-X which has Security Plus license and supports unlimited interfaces.

The CBD firewall was configured with four zones:
- outside (Gig1/1): faces CBD-RTR-01, security level 0
- dmz-auth (Gig1/2): faces CBD-AUTH-01, security level 50
- dmz-data (Gig1/3): faces CBD-DATA-01, security level 50
- inside (Gig1/4): faces CBD-SW-01, security level 100

We also tried placing firewalls at Clayton and Mernda but ran into another Packet Tracer limitation. The ASA 5506-X does not support VLAN sub-interfaces on physical ports in the simulation, which meant VLAN-tagged traffic from the switch could not pass through the firewall to reach the router sub-interfaces. After multiple failed attempts to work around this the group decided to remove the campus firewalls at Clayton and Mernda. The CBD firewall handles security for the headquarters network and DMZ. The branch campuses rely on the VPN encryption and router ACLs for protection.

---

## Access control lists

ACLs were configured on all campus routers and the CBD core switch to block unwanted cross-VLAN traffic. The rules applied on every campus are:

- Guest devices cannot reach Admin, Doctor, or IoT networks
- IoT devices cannot reach Doctor or Guest networks
- Doctor devices cannot reach Guest network
- All other traffic is permitted

ACLs were applied inbound on router sub-interfaces for Clayton and Mernda, and on VLAN interfaces on the CBD core switch. Testing with Simple PDU confirmed that guest phones could not ping admin or doctor PCs on any campus.

---

## Inter-campus routing

Static routes were added to all routers so each campus can reach the others through the ISP router. Each campus router has a default route pointing to the ISP. The ISP router has specific routes to all campus subnets.

Connectivity tests after routing configuration:

- Clayton to CBD: successful
- Clayton to Mernda: successful
- Mernda to CBD: successful
- CBD to Clayton: successful
- CBD to Mernda: successful

---

## IPSec VPN

The Cisco 2911 routers do not have the security license enabled by default. The group enabled it on all three campus routers using:

```
license boot module c2900 technology-package securityk9
```

Each router was reloaded after accepting the license agreement.

VPN tunnels were configured with the following parameters:

- Encryption: AES 256
- Hash: SHA
- Authentication: Pre-shared key
- Diffie-Hellman group: 2
- Lifetime: 86400 seconds
- Transform set: ESP-AES-256 with ESP-SHA-HMAC

VPN status after configuration:

- Clayton to CBD: active, tunnel established, traffic encrypting (QM_IDLE confirmed)
- Mernda to CBD: configured, pending final verification
- Clayton to Mernda: configured but tunnel not establishing (see errors below)

---

## Errors encountered

**Error 1: ASA 5505 interface limit**
The ASA 5505 in Packet Tracer only supports 2 named interfaces. We could not create a DMZ zone. Fixed by replacing with ASA 5506-X.

**Error 2: ASA DHCP conflict**
When assigning an IP to Vlan1 on the ASA, we got an error saying the address was not on the same subnet as the default DHCP pool. Fixed by removing the default DHCP pool first using `no dhcpd address`.

**Error 3: Cloud-PT not routing**
The Cloud-PT device requires internal port mapping to pass traffic between connected devices. It does not route automatically. Fixed by removing the cloud and using the ISP router directly.

**Error 4: VPN crypto commands not recognised**
The security license was disabled by default on the 2911 routers. Crypto commands returned invalid input errors. Fixed by enabling the securityk9 license and reloading.

**Error 5: DHCP not working**
The ASA firewall blocks DHCP relay broadcasts between security zones. Devices received APIPA addresses (169.254.x.x) instead of the correct subnet. Fixed by switching all end devices to static IP.

**Error 6: Campus firewall blocking VLAN traffic**
The ASA 5506-X does not support sub-interfaces on physical ports in Packet Tracer. VLAN-tagged traffic from the switch could not pass through the firewall. Fixed by removing campus firewalls at Clayton and Mernda.

**Error 7: Trunk encapsulation error on 3560**
When setting Fa0/9 to trunk mode on the 3560 switch we received an error saying the interface encapsulation is Auto and cannot be set to trunk. Fixed by running `switchport trunk encapsulation dot1q` before `switchport mode trunk`.

**Error 8: Clayton to Mernda VPN not establishing**
The ISAKMP negotiation between Clayton and Mernda stays at MM_NO_STATE. Debug output confirmed Mernda is sending IKE packets but Clayton never receives them in the simulation. The CBD to Clayton tunnel works fine. This appears to be a Packet Tracer simulation limitation for direct router to router IPSec without an intermediate firewall device. Routing between Clayton and Mernda works correctly without VPN.

---

## Decisions made this week

We removed campus firewalls at Clayton and Mernda because the ASA sub-interface limitation made VLAN routing through the firewall impossible in Packet Tracer. In a production environment each branch would have a proper next-gen firewall.

We switched to static IPs after DHCP consistently failed due to the firewall blocking relay traffic.

We removed the Cloud-PT device and used the ISP router as the internet representation after confirming the cloud does not support native routing.

We upgraded from ASA 5505 to ASA 5506-X to get the Security Plus license needed for the DMZ.

---

## After meeting - future enhancements

These items were identified during this week's session and will be noted as future improvements in the final report.

**Backup server**
A second database server should be added to replicate CBD-DATA-01. If the primary goes down the backup takes over. This was not implemented due to budget constraints but is flagged as a priority enhancement for the next phase.

**Campus firewalls**
Clayton and Mernda should each have a dedicated next-gen firewall such as Cisco Firepower that properly supports VLAN sub-interfaces and zone-based policy. The current design leaves branch campuses without dedicated perimeter protection.

**DHCP server**
A dedicated DHCP server in the DMZ with ip helper-address configured on each campus router would remove the need for static IP addressing and make device onboarding faster.

**Redundant firewall**
CBD-FW-01 is a single point of failure. An Active/Standby HA pair would provide automatic failover with no downtime if the primary fails.

**Clayton to Mernda direct VPN**
The direct IPSec tunnel between Clayton and Mernda could not be established in the simulation. In production this would either be resolved through proper IKE negotiation or handled by routing all branch to branch traffic through the CBD firewall in a hub and spoke VPN design.

**WLC integration**
The WLC at CBD was placed but not fully integrated. In production it would centrally manage all access points across all three campuses with consistent wireless policies.

---

## Week summary

- Device placement and cabling: done
- VLAN configuration on all campuses: done
- Inter-VLAN routing: done
- Wireless on all campuses: done
- ACLs on all campuses: done
- Static IPs on all devices: done
- Inter-campus routing: done
- CBD firewall and DMZ: done
- IPSec VPN Clayton to CBD: done and active
- IPSec VPN Mernda to CBD: configured, pending test
- IPSec VPN Clayton to Mernda: configured, tunnel issue noted
- Final connectivity test: next session

---

Log maintained by the MMHN project team
Next session: complete VPN verification, final connectivity testing, documentation
