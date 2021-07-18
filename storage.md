
### <a name="storage"></a>Storage Unit
- Able to store large volume of data.
- Data can be divided into two main categories. Private and Public. The tag "private" and "public" doesn't represent its accessibility.
- Public data examples: movies, games, music, OS, propriety software. Basically stands for certain files which could be easily reproduced and doesn't pose security risk.
- Private is for the data that is more strict and sensitive, hence the name. Files, folders and dir's marked with "private" have strict file system rules such as deletion, read, write, delete action requires confirmation from [Biometric confirmation unit](#biometric-confirmation-unit)
- So far, it is decided that NextCloud will get the job done fairly easily.
- Method of interaction with the storage unit can be done via several ways:
    1. Local Access
        - FTP/sFTP
        - Software Interface (NextCloud, OpenMediaVault)
    2. Remote Access
        - Through [Exposer](#exposer)

- For now, all access requires authentication by standard means.
- In the ultimate form, this module should use RAID 10 (RAID 1+0)
