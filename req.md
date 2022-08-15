## Glossary
- <a name="ecosystem"></a> **Ecosystem:** Container for all users and modules, doesn't include remote entities.  
- <a name="master"></a> **Master**: User/person with the ultimate authority, sole owner of the system. At any time, there can only be one Master.
- <a name="module"></a> **Module**: Each individual service is named module. E.g: [Storage solution](/storage/storage.md), [Biometric confirmation unit](/biometric-confirmation-unit/biometric-confirmation-unit.md) etc.

## List of requirements:
- Modules
    - [Storage Unit](/storage/storage.md)
    - An [access manager](/access-base/access-base.md), versatile and robust. Similar to ACL
    - Spider/Crawler crypt
    - Media hub(Plex, Kodi, Streamio)
        - For music: 
            - HiFiBerryOS doesn't support listening from web, yikes.
            - mopidy, Volumio, GrooveBasin
            - navidrome, Lightweight Music Server (LMS), Subsonic, Airsonic advanced
            - plex, kodi ?
    - Broadcast station (uhf/vhf, maybe using LoRa hat)  
    - Radio, Aircraft signals receiver  
    - External Access Manager (Exposer) and Firewall
    - Counter measures arsenal
    - Getaway/Sandbox device
    - [Web server](/web-server/web-server.md)
    - p2p, Media fetcher (torrent box, ddl links)
    - Telemetry (Physical and virtual), logging, probing (features sense hat too)
    - Overseer (mainframe), set of rules and actions 
    - DNS server (pi-hole or dnsmasq)
    - [Biometric confirmation unit](/biometric-confirmation-unit/biometric-confirmation-unit.md)
    - [Router](/router/router.md) (Canceled for now)
    - Intranet Wiki (by DokuWiki)
    - Password vendor. (D.I.Y or BitWarden)
    - Sync server (syncthing)
    - Search Engine (searx)
    - OSINT

- Legislation/Canonical
    - [Constitution](/constitution/constitution.md)
    - Possible scenarios (Globals, End of the line, intrusions, Abrupt FIN, physical intervention etc.) Predefined instruction sets.
    - [Backup plan](/backup-plan/backup-plan.md)
    - [Connection standards](/connection-standards/connection-standards.md)

---

- **Prometheus** is a great solution for monitoring. Single main instance can collect data from other instances (node_exporter)
- Later on these could be shown in nice graphics using **Grafana**
- Prometheus is incredible tbh


- Respeaker HAT for speaker (kinda amplified) output and built in mic.



## Priorities
- DNS server
- Spider/Crawler Crypt
- Telemetry
- Web server
