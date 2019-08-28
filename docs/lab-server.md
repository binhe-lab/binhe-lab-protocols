---
title: Lab server How-To
author: Bin He
date: 2018-08-26
categories: 
 - Basics
tags: 
 - bioinfo
---

# Function of lab servers

The lab servers serve three functions:

1. Allow users to transfer data from the shared computers in the Carver Center for Genomics (CCG) and Carver Center for Imaging (CCI).
1. Allow members of the lab to collaborate easily by sharing data.
1. Store all raw data safely. If you have a piece of raw data that is only stored on your personal computer, it is wrong! 

Note that we store semi-processed data and analysis codes and results using project [GitHub](https://github.com/binhe-lab) repository.

We have two storage servers available. LSS is used for remote computing on the Argon cluster. All other data transfer and storage uses RDSS.

# Request access to the lab servers

Once you join the lab, ask the [Biology IT group](mailto:biology-help-sm@uiowa.edu) to add you to our security group, cc [Bin](mailto:bin-he@uiowa.edu) on your email. It may take a day or two for the security group to be updated so you can access the lab servers. If in doubt, ask Bin.

The lab servers can be accessed by several means:

- Map as a folder on your personal and any university provided computers
- Mount on Linux systems
- Access on HPC (server)
- FTP clients
    
## Map RDSS as a folder (drive)

RDSS is used for everything except for next generation sequencing data storage, analysis or other computation that requires access to the high performance computing cluster ([Argon](https://wiki.uiowa.edu/display/hpcdocs/Argon+Cluster))

_Note: on CCG computers, look for a folder on the desktop under the name "He", and there should be a shortcut inside that allows you to map the drive. If not, right click on the "Computer" icon and choose "Map Network Drive". Put in the address and credentials as shown below_

**Table 1  RDSS mounting as a folder**

| OS | Menu item | Address |
|----|--------|------|
| Mac | Finder -> Connect to server... | smb://IOWA;HawkID@iowa.uiowa.edu/shared/researchdata/rdss_bhe2 |
| Linux | File manager -> Ctrl+L | smb://IOWA;HawkID@iowa.uiowa.edu/shared/researchdata/rdss_bhe2 |
| Windows | [Instructions](https://its.uiowa.edu/support/article/102465) | \\\\iowa.uiowa.edu\shared\researchdata\rdss_bhe2 |

- replace "HawkID" with your actual HawkID, but don't change the "bhe2"s
- on Windows machines, tick the box that says "log in as a different user name", then click "Connect". The system will ask you for your username and password. FOr username, use the following format `IOWA\HawkID`, e.g. `IOWA\bhe2`.
- if you are off campus, you may need to be connected to the VPN client in order to gain access. Follow the instructions on this [article](https://its.uiowa.edu/support/article/1876)


This approach allows you to interact with the lab server as if it were an additional folder on your personal computer. Once it's connected, you will see the following folder structure:

```
.
├── Core
├── Project
└── User
```

For work related to a specific project, use of the `Project` folder is preferred. For things that don't fall under a single project, use the folder under your name in the `User` folder.

## Command line mounting

_Note: If you use one of the lab provided linux desktops, once you log in, use the command line to navigate to `/mnt/nfs/lss_grelab` for LSS and to `/mnt/cifs/rdss/rdss_bhe2` for RDSS, and you would have full access to the server space._

If you are using your personal computer running Linux / Mac OS, use the following command to mount LSS

```bash
# LSS
mount -t cifs -o username=HawkID,sec=ntlm,domain=iowa,uid=$(id -u $(whoami)),gid=$(id -g $(whoami)) //lc-rs-storage17.hpc.uiowa.edu/grelab /mnt/cifs/lss_grelab

# RDSS
mount -t cifs -o username=HawkID,domain=iowa,uid=$(id -u $(whoami)),gid=$(id -g $(whoami)) //rdss.iowa.uiowa.edu/rdss_bhe2 /mnt/cifs/rdss_bhe2 
# the additional uid and gid options are required so that the cifs client knows that these are the uid and gid for the user that matches the uid and gid on the server, which can be different.
```

## Access LSS on HPC

LSS is mounted automatically under `/Shared/grelab`

## FTP

To download or upload files onto LSS server, use the following instructions:

`data.hpc.uiowa.edu` with HawkID and password. The LSS share will be automounted under `/Shared/grelab`

Download a FTP client such as [FileZilla](https://filezilla-project.org/), and point to `data.hpc.uiowa.edu`, login with your HawkID credentials.

## Map LSS as a folder

_Note that LSS is meant to be accessed through the HPC clusters. If you need to download or upload files, FTP is recommended over mapping as a folder._

**Table 2  LSS mounting**

| OS | Menu item | Address |
|----|--------|------|
| Mac | Finder -> Connect to server... | smb://IOWA;**HawkID**@lc-rs-storage17.hpc.uiowa.edu/grelab |
| Windows | [Instructions](https://its.uiowa.edu/support/article/102465) | \\\\lc-rs-storage17.hpc.uiowa.edu\grelab |
| Linux<sup>1</sup> | File manager -> Ctrl+l | smb://IOWA;**HawkID**@lc-rs-storage17.hpc.uiowa.edu/grelab |

- *replace "HawkID" with your actual HawkID, but don't change the "bhe2"s*
- *Note that if you are off campus, you may need to be connected to the VPN client in order to gain access. Follow the instructions on this [article](https://its.uiowa.edu/support/article/1876)*

# FAQ

1. What's the difference between RDSS and LSS?

    These two storage servers are both provided and managed by the Information Technology Services. RDSS, standing for Research Data Storage Service, is managed by the [ITS Enterprise Services](https://its.uiowa.edu/about/es). It provides 5TB for free, with 24/7 tech support. It is not accessible, however, on the High Performance Computing clusters. LSS, or Large Storage Service, is offered and managed by the HPC Sysadmins. All UI3 associated labs get 5 TB of LSS storage. Its technical support is business hours only. It is available on the HPC system.

    Below is a chart of comparison, also see [here](https://its.uiowa.edu/researchstorage)

    **Table 3 Comparison of RDSS and LSSS**
     
    |  | RDSS | LSS |
    |--|--|--|
    | Website | <https://its.uiowa.edu/rdss> | <https://its.uiowa.edu/lss> |
    | Space | 5 TB | 5 TB |
    | Use   | Desktop file sharing | Desktop file sharing & HPC |
    | Backups | Yes | Optional |
    | Snapshops | Daily | HPC: Hourly, Daily, Monthly; Non-HPC: daily | 
    | Backup retention | 30 days | 30-90 days |
    | Email, general | <its-etm@uiowa.edu> | <hpc-sysadmins@iowa.uiowa.edu> |
    | Contact person | Ryan West at ITS-ETM | John Sexton at <john-sexton@uiowa.edu> |
    | Request permission change | [RDSS Security change form](https://uiowa.qualtrics.com/SE/?SID=SV_8qyutD7sDdwnOoB) | email <hpc-sysadmins@iowa.uiowa.edu> |
    

2. In Linux/Mac OS, is the "map as a folder" the same as "command line mount"? Where are they in the file system?

    The main difference between the two is that the former method uses GVfs (GNOME Virtual file system) as part of the GNU library while the latter uses the `mount` function in the kernel. When "connect to server" in the GUI is used, the mount point in recent Linux versions (circa 2018, tested in Fedora+MATE and Ubuntu 16.04) is `/run/user/$UID/gvfs/`. When `mount` command is used, the user specifies the mount position. Since these are simply different "portal" for the same windows share, they should be synced.
