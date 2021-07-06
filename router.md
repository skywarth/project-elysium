# Router

//=============================================================

- // ABORTED FOR NOW.
- // It might not be possible to use raspberry or similar SBC's.
- /* Many implementations feature AP, Wi-Fi hotspot etc. Not like an actual WAN DHCP router. */ 

//=============================================================


This module is expected to be one device. Main purpose is to furnish the system with:

- LAN and a workspace
- Access to WAN (Internet) and capability to share it to local network.
- Port forwarding
- Allows connection through Ethernet (RJ-45) and WiFi (802.11n).
- Ability to allow/disallow connected endpoints. 

*In essence it's just a conventional router hun c'mon*

But since [telemetry](/telemetry.md) is paramount, and privacy section as defined in [constitution](/constitution.md#core-principles) it is not feasible to use conventional router interfaces. Conventional router OS's and interfaces will not suffice the required security, privacy and customization needs. 


### OS/Software Candidates:
- OpenWrt
- VyOS
