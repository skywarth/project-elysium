# <a name="backup-plan"></a> Backup plan

## Backup standards




### Naming Conventions
- All backups files should follow the given naming pattern:
```
{YYYYMMDD}_{hostname}_{type}
# e.g: "20151123_suzieq_partial" (folder)
# e.g: "20150906_suzieq_full.img"
```

- In case of a need for elevated amount of backups (twice per day), use unix timestamps.

### Extensions
- tar.gz is preferred since there are a lot of sub-folders. It takes years with zip. Compression is not paramount after all. Might as well cancel gzip too. 


### Backup Locations
- Local backups: 
  - ```/home/{user}/local_backups/{file or folder name}```
  - ```/home/{user}/local_backups/{file or folder name}.tar.gz```
  - tar.gz one is created following the generation of backup file/folder. After that, original backup file/folder shall be deleted.


- Remote backups:
  - ```{[Storage unit](/storage.md) IP}/pi_backups/{hostname}/rsync/{backup_file name or folder name}```
  - ```{[Storage unit](/storage.md) IP}/pi_backups/{hostname}/img/{backup_file name or folder name}```
  


## Manual backups:

- **[!]** After clean installation of each individual module, master is tasked with creating an image of the prepared instance. Cloning/Imaging tool candidates:
    - AOMEI
    - BalenaEtcher seems pretty good and easy. //only for recovery, not creating image
    - CloneZilla
    - Paragon
    - MondoRescue
    - Acronis
   
## Automated backups

1. ### Partial backup