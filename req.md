## Glossary
- 

## List of requirements:
- [Storage solution](#storage)
- An access manager, versatile and robust. Similar to ACL [1]
- Spider/Crawler crypt
- Media hub, broadcast
- External Access Manager (Exposer) and Firewall
- Counter measures arsenal
- Getaway/Sandbox device
- Web server
- p2p device
- Telemetry (Physical and virtual)
- Overseer (mainframe), set of rules and actions 
- DNS server
- [Biometric confirmation unit](#biometric-confirmation-unit) 
- Possible scenarios (Globals, End of the line, intrusions, Abrupt FIN, physical intervention etc.) Predefined instruction sets.

---

### <a name="storage"></a>Storage Solution
- Able to store large volume of data.
- Data can be divided into two main categories. Private and Public. The tag "private" and "public" doesn't represent its accessibility.
- Public data examples: movies, games, music, OS, propriety software. Basically stands for certain files which could be easily reproduced and doesn't pose security risk.
- Private is for the data that is more strict and sensitive, hence the name. Files, folders and dir's marked with "private" have strict file system rules such as deletion, read, write, delete action requires confirmation from [Biometric confirmation unit](#biometric-confirmation-unit)
- So far, it is decided that NextCloud will get the job done fairly easily. 
- Method of interaction with the storage solution can be done via several ways:
    1. Local Access
        - FTP/sFTP
        - Software Interface (NextCloud)
    2. Remote Access
        - Through [Exposer](#exposer)
    
- For now, all access requires authentication by standard means.     


### <a name="biometric-confirmation-unit"></a> Biometric Confirmation Unit

Various events and actions require biometric confirmation unit to be invoked in order to proceed. 

- In essence this is a simple device with two physical input interfaces. One is for basic keyboard input, other is for actual biometric input. 
- Aim is to assure action that requests permission was initiated by authentic user. 
- Biometric input is not really expected to be implemented in the first iterations. Keyboard input alone should be enough. After all; we are trying to stop bots and imposters in the first place.
- Keyboard input is used to provide some sort of master key. This master key is stored and compared to input made by the keyboard. 
- Means of storage for the password is some sort of custom hashing function. vanillaCrypt project could prove useful for this instance. Even tough decryption was never implemented in that, there is no need for it. Only input hash and stored hash will be compared. It was a mashup of established encryption algorithms such as AES, DES etc. I think it'll suffice.