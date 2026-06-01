# Week 12 - Lab Session Journal

COIT13236 | Melbourne Metro Health Network (MMHN)
HT1 2026 | Central Queensland University

Team: Ashikha Pakkiru, Kunj Patel, Kunj Acharya, Masum Patel

---

## Overview

Week 12 focused on continuing the physical prototype setup and progressing toward correct IP assignment across all three campus representations. The session built on the basic connectivity established in the previous week and moved toward configuring each TP-Link router with an IP address that matches the MMHN logical design.

---

## Physical Setup

The physical prototype this week used the following equipment:

- 3x TP-Link Archer C24 routers
- 3x Cisco Catalyst 3560-CX switches
- 1x laptop (CBD campus device)
- 2x university lab PCs (Clayton and Mernda campus devices)

The topology was configured as follows:

- Wall outlet provides internet to TP-Link 1 (CBD router) via WAN port
- TP-Link 2 (Clayton router) connects to TP-Link 1 via LAN port
- TP-Link 3 (Mernda router) connects to TP-Link 1 via LAN port
- Each TP-Link router connects to its respective Cisco switch
- Each switch connects to its respective end device

This mirrors the hub and spoke topology from the logical design where CBD acts as the central hub and Clayton and Mernda connect through it.

---

## IP Assignment

The group configured correct IP addresses on two of the three campus routers to match the MMHN addressing scheme.

**Clayton IP configuration**

<img width="890" height="870" alt="Clayton ip configured" src="https://github.com/user-attachments/assets/2747d50c-2c49-4c97-a681-3b9515f18e44" />

**Clayton Ping Confirmed**

<img width="547" height="287" alt="clayton router ping confirm" src="https://github.com/user-attachments/assets/63a99883-8170-40e8-a78a-c48b4281b7de" />


**CBD Campus (TP-Link 1)**

The router LAN IP was changed from the default 192.168.0.1 to 192.168.10.1 through the TP-Link web interface. The laptop was assigned a static IP of 192.168.10.10 with a gateway of 192.168.10.1. Connectivity was verified with a successful ping test showing 100% success and 0% packet loss.

Commands used on laptop:

<img width="1300" height="947" alt="cbd router configured router ip" src="https://github.com/user-attachments/assets/9051e7fb-2395-42a1-bfc9-4622ba9a9e28" />

```
netsh interface ip set address "Ethernet" static 192.168.10.10 255.255.255.0 192.168.10.1
ping 192.168.10.1
```
**CBD Ping**

<img width="778" height="353" alt="cbd configured router ping" src="https://github.com/user-attachments/assets/32b8e078-b9c4-407d-98ba-8c137e5e7ae0" />


**Clayton Campus (TP-Link 2)**

The router LAN IP was changed from the default 192.168.0.1 to 192.168.11.1 through the TP-Link web interface. The connected computer received an IP of 192.168.11.100 via DHCP from the router. Connectivity was verified with a successful ping test.

---

## Errors Encountered

**Error 1: ACS virtual machine could not access physical ethernet**
The ACS virtual machine on the university PCs uses virtual network adapters that are not bridged to the physical ethernet port. Devices connected to the physical switch could not be reached from inside ACS. The group attempted to set static IPs inside ACS but traffic was being routed through the host-only virtual adapter instead of the physical ethernet. This is a virtualisation limitation of the ACS environment.

Resolution: The unit coordinator confirmed it is acceptable to demonstrate connectivity from the host machine directly rather than through ACS for the physical prototype evidence.

**Error 2: Laptop wifi routing traffic instead of ethernet**
When pinging the router from the laptop, replies were coming from 10.178.36.1 (university WiFi gateway) instead of the TP-Link router. This was because Windows was routing traffic through the WiFi interface instead of the ethernet interface.

Resolution: WiFi was disabled temporarily to force all traffic through the ethernet adapter connected to the switch.

**Error 3: Switch console driver not detected**
The group attempted to configure the Cisco 3560-CX switch via console cable using PuTTY. The USB to console adapter was not recognised in Device Manager, meaning the COM port was not available for PuTTY to connect to.

Resolution: Switch configuration was deferred to the next session. The switch operated in its default state passing traffic transparently, which was sufficient for basic connectivity testing this week.

---

## Decisions Made

The group decided to use the host machine directly for ping tests and IP verification rather than ACS, following confirmation from the unit coordinator that this is acceptable for prototype evidence purposes.

Switch VLAN configuration was deferred to the next session pending resolution of the console cable driver issue.

---

## Connectivity Verified

- Laptop (192.168.10.10) to CBD router (192.168.10.1): successful, 0% packet loss
- Computer 2 (192.168.11.100) to Clayton router (192.168.11.1): successful

---

## After Meeting - Remaining Tasks

The following tasks were not completed this session and are carried forward:

**Mernda campus IP assignment**
TP-Link 3 still needs its LAN IP changed to 192.168.12.1 and the connected computer needs to be assigned 192.168.12.10.

**Switch VLAN configuration**
The Cisco 3560-CX switches need to be configured with VLANs 10, 20, 30 and 40 to match the logical design. This requires the console cable driver to be installed and working.

**Security configuration**
All three TP-Link routers need basic security hardening including password changes, WPA2 wireless security, and disabling unused features.

**IP routing between campuses**
Once all three routers have correct IPs, routing between the three campus networks needs to be verified through ping tests.

**Video evidence**
A short video documenting the physical setup, cable connections, and configuration steps still needs to be recorded.

---

## Week Summary

- Physical topology connected and working: done
- CBD router IP changed to 192.168.10.1: done
- Clayton router IP changed to 192.168.11.1: done
- Mernda router IP assignment: pending
- Switch VLAN configuration: pending
- Security configuration: pending
- Inter-campus routing verification: pending
- Video evidence: pending

---

Log maintained by the MMHN project team
Next session: complete Mernda IP assignment, switch VLANs, security configuration, and inter-campus routing verification
