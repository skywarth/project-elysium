## Glossary
- <a name="ecosystem"></a> **Ecosystem:** Container for all users and modules, doesn't include remote entities.  
- <a name="master"></a> **Master**: User/person with the ultimate authority, sole owner of the system. At any time, there can only be one Master.
- <a name="module"></a> **Module**: Each individual service is named module. E.g: [Storage solution](/storage.md), [Biometric confirmation unit](/biometric-confirmation-unit.md) etc.

## List of requirements:
- [Storage solution](/storage.md)
- An [access manager](/access-base.md), versatile and robust. Similar to ACL
- Spider/Crawler crypt
- Media hub, broadcast (Plex, Kodi, Streamio)
- Radio, Aircraft signals  
- External Access Manager (Exposer) and Firewall
- Counter measures arsenal
- Getaway/Sandbox device
- [Web server](/web-server.md)
- p2p device
- Telemetry (Physical and virtual), logging, probing
- Overseer (mainframe), set of rules and actions 
- DNS server (pi-hole or dnsmasq)
- [Biometric confirmation unit](/biometric-confirmation-unit.md) 
- Possible scenarios (Globals, End of the line, intrusions, Abrupt FIN, physical intervention etc.) Predefined instruction sets.
- [Backup plan](/backup-plan.md)
- [Connection standards](/connection-standards.md)
---

- **Prometheus** is a great solution for monitoring. Single main instance can collect data from other instances (node_exporter)
- Later on these could be shown in nice graphics using **Grafana**