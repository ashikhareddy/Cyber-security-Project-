# Week 10 — Network Configuration & File Sharing Lab

## Overview
This week focused on setting up a small office network using physical hardware (Cisco switch, TP-Link routers, UniFi access point) and configuring Windows networking features including network discovery, file sharing, and connectivity troubleshooting between hosts.

## Hardware Used
- Cisco Catalyst 3560-CX Series switch
- 2x TP-Link wireless routers
- Ubiquiti UniFi UAP-AC-LITE access point
- Dell OptiPlex workstation
- Cat6 patch cables (blue, yellow, green, white)

## Tasks Completed

### 1. Physical Network Setup
Cabled the lab topology connecting the workstation through the Cisco Catalyst switch to the TP-Link routers and UniFi AP. Verified link lights on switch ports and confirmed PoE-powered devices came up correctly.




### 2. IP Configuration & Connectivity Testing
Ran `ipconfig /all` on the ACS-VM to confirm the host received the correct IP (192.168.56.1) on the Ethernet 3 adapter. Initial `ping 192.168.1.1` returned "Destination host unreachable" — traced this to a missing route / wrong subnet. After correcting the adapter configuration, `ping 192.168.1.2` returned 4/4 replies at 1ms TTL=128.

```cmd
C:\Users\ACS>ping 192.168.1.2

Pinging 192.168.1.2 with 32 bytes of data:
Reply from 192.168.1.2: bytes=32 time=1ms TTL=128
Reply from 192.168.1.2: bytes=32 time=1ms TTL=128
Reply from 192.168.1.2: bytes=32 time=1ms TTL=128
Reply from 192.168.1.2: bytes=32 time=1ms TTL=128

Ping statistics for 192.168.1.2:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 1ms, Maximum = 1ms, Average = 1ms
```

### 3. Changing Network Profile (Public to Private)
By default, the new connection was flagged as a Public network, which blocks file sharing and discovery. Used PowerShell as Administrator to switch it to Private:

```powershell
Get-NetConnectionProfile
Set-NetConnectionProfile -Name "Unidentified network" -NetworkCategory Private
Get-NetConnectionProfile
```

Confirmed `NetworkCategory : Private` after the change.

### 4. Folder Sharing Configuration
- Right-clicked the target folder, selected **Give access to > Specific people...**
- Added the `Everyone` group with **Read/Write** permission
- Clicked **Share** and recorded the network path (`\\ACS-VM\masum`)
- Verified the share was reachable from another host on the same subnet

## Issues & Troubleshooting
- **"Destination host unreachable"** on first ping — caused by the adapter being on the wrong subnet. Resolved by checking `ipconfig` and reconnecting to the correct switch port.
- **File share not visible** initially — caused by Public network profile blocking SMB. Resolved by switching the profile to Private (see step 3).

## Key Takeaways
- Always check the network profile (Public vs Private) before troubleshooting share/discovery issues — it's the most common cause of "I can't see the other PC".
- `ping` failures aren't always cabling — verify L3 (IP/subnet) before re-crimping cables.
- Granting `Everyone` Read/Write is fine for a lab but should never be used in production; use named users or AD groups instead.

## Next Week
- Configure VLANs on the Cisco 3560-CX
- Set up the UniFi AP with a controller and test wireless client roaming
