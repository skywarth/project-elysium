## Glossary
- <a name="ecosystem"></a> **Ecosystem:** Container for all users and modules, doesn't include remote entities.  
- <a name="master"></a> **Master**: User/person with the ultimate authority, sole owner of the system. At any time, there can only be one Master.
- <a name="module"></a> **Module**: Each individual service is named module. E.g: [Storage solution](#storage), [Biometric confirmation unit](#biometric-confirmation-unit) etc.

## List of requirements:
- [Storage solution](/storage.md)
- An [access manager](#access), versatile and robust. Similar to ACL
- Spider/Crawler crypt
- Media hub, broadcast (Plex, Kodi, Streamio)
- Radio, Aircraft signals  
- External Access Manager (Exposer) and Firewall
- Counter measures arsenal
- Getaway/Sandbox device
- Web server
- p2p device
- Telemetry (Physical and virtual), logging
- Overseer (mainframe), set of rules and actions 
- DNS server
- [Biometric confirmation unit](#biometric-confirmation-unit) 
- Possible scenarios (Globals, End of the line, intrusions, Abrupt FIN, physical intervention etc.) Predefined instruction sets.
- Backup tools
---

### <a name="access"></a> Access Base
User roles, role groups, permissions are all defined here. For permission checks (other than biometric confirmation), every module visits Access Base.

- All the data regarding permissions, roles and similar will be retained in a conventional database (SQL based). 
- An API is needed to perform role checks, permission validations, or alterations. Otherwise, directly sending sql queries to this module is both dangerous and clunky.
- Good candidate for API is Lumen. Simple and lightweight. Alternative is NodeJS.
- If some sort of proper interface is required or advanced capabilities is a must, then Laravel is a good fit. Alternative NodeJS, or some Python framework (Flask ?).
- The API is expected to be lighting fast since big chunk of actions and functions eventually hit this endpoint. 
- This module is closed to remote access by all means.
#### Definitions:
**Permission:** Single instruction that testifies a permit to do an action. Examples: 'Read public file from [Storage](#storage)', 'Edit [Exposer](#exposer) settings'

**Role:**  Slugs/tags for each user and [module](#) in the ecosystem. For the sake of simplicity each user has one role: ```(n)user->(1)role``` . Of course there can be other users or modules with the same role. Example: 'guest','master','local master','telemetry module'. Allowing multiple roles per user is still in consideration.

**Role Permissions:** Standard permissions for a given role. Example
Master Permissions: 'Edit [overseer](#overseer)', 'Initiate FIN protocol', 'Read telemetry data' etc.
Guest permissions: 'Connect to dns server', "connect to media hub's broadcast"
```(n)role->(n)permission```

**User Permissions:** Each user/module gets its permissions from two sources. One is inheriting from given role's permissions, other is from exclusive permissions. 
```
Example scenario:
- Guest permissions: "Connect to dns server", "connect to media hub's broadcast"
- User #46 is a user with "Guest" role
- User #46 is given the exclusive permission: "Access web server on port:80"
- User #46's permissions: "Connect to dns server", "connect to media hub's broadcast", "Access web server on port:80"

```

---


### <a name="web-server"></a> Web Server
This module is responsible for running web applications. The web applications to run cannot be another module's dependency. Think this one as a sandbox web server environment. By default, remote connections are refused as usual.

- Sandbox web server environment
- Main goal is to equip the master with the capability to test web applications in a wide range of environments.
- Therefore, this module consists of many devices as a member.
- Each device is featuring a distinct web server environment. Examples:
    - **LAMP**: Apache2 + Nginx server with PHP and MySQL installed and ready. Running a common Linux distro (CentOS, Ubuntu etc.)
    - **MEAN/MEVN/MERN**: CentOS with NodeJS, MongoDB, NPM, Yarn, Gulp.
    - **WIN**: Windows server with MSSQL installed
    - **RUBY**: Ruby, Node.js, Yarn, Gem, some Linux distro
    
- **[!]** After clean installation, master is tasked with creating an image of the prepared web service device instance. Cloning/Imaging tool candidates:
    - AOMEI
    - CloneZilla
    - Paragon
    - MondoRescue
    - Acronis
    

### <a name="biometric-confirmation-unit"></a> Biometric Confirmation Unit

Various events and actions require biometric confirmation unit to be invoked in order to proceed. 

- In essence this is a simple device with two physical input interfaces. One is for basic keyboard input, other is for actual biometric input. 
- Aim is to assure action that requests permission was initiated by authentic user. 
- Biometric input is not really expected to be implemented in the first iterations. Keyboard input alone should be enough. After all; we are trying to stop bots and imposters in the first place.
- Keyboard input is used to provide some sort of master key. This master key is stored and compared to input made by the keyboard. 
- Means of storage for the password is some sort of custom hashing function. vanillaCrypt project could prove useful for this instance. Even tough decryption was never implemented in that, there is no need for it. Only input hash and stored hash will be compared. It was a mashup of established encryption algorithms such as AES, DES etc. I think it'll suffice.
- Since hard-confirmation won't be too common in the system, it might be a good idea not to implement auth caching.