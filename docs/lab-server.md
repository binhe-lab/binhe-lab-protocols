---
title: Lab server How-To
author: Bin He
date: 2018-08-26
categories: Basics
tags: bioinfo
---

# Function of lab servers

All data produced in the lab, including raw data and analyses, should be stored on the lab server, which can be mapped as an external drive on your personal or lab computers. The only exception is when the data and analyses are synced to the project [GitHub](https://github.com/binhe-lab) repo. Storing data on the lab servers ensures that data are safe and organized. More importantly, it allows the lab to work together on joint projects.

# Overview of lab servers

There are two major lab servers, provided and managed by different departments at the Information Technology Services. RDSS, standing for Research Data Storage Service, is managed by the [ITS Enterprise Services](https://its.uiowa.edu/about/es). It provides 5TB for free, with 24/7 tech support. It is not accessible, however, on the High Performance Computing clusters. LSS, or Large Storage Service, is offered and managed by the HPC Sysadmins. All UI3 associated labs get 5 TB of LSS storage. Its technical support is business hours only. It is available on the HPC system.

Below is a chart of comparison, also see [here](https://its.uiowa.edu/researchstorage)

Table 1 Comparison of RDSS and LSSS

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

# How to use the RDSS and LSS servers

Once you join the lab, ask the [Biology IT group](mailto:biology-help-sm@uiowa.edu) to add you to our security group. It may take a day or two for the security group to be updated so you can access the lab servers. If in doubt, ask Bin.

The lab servers can be accessed by several means:

- Map as a folder
- Mount through the command line
- Access on HPC (server)
- FTP clients
    
Note that if you are off campus, you may need to be connected to the VPN client in order to gain access. Follow the instructions on this [article](https://its.uiowa.edu/support/article/1876)

Next we discuss each method for the two types of storage separately.

## Map the lab server as a folder

This approach allows you to interact with the lab server as if it were an additional folder on your personal computer.

Table 2  RDSS mounting as a folder

| OS | Menu item | Address |
|----|--------|------|
| Mac | Finder -> Connect to server... | smb://IOWA;HawkID@iowa.uiowa.edu/shared/researchdata/rdss_bhe2 |
| Linux | File manager -> Ctrl+l | smb://IOWA;HawkID@iowa.uiowa.edu/shared/researchdata/rdss_bhe2 |
| Windows | [Instructions](https://its.uiowa.edu/support/article/102465) | \\iowa.uiowa.edu\shared\researchdata\rdss_hawkID |

Table 3  LSS mounting

| OS | Menu item | Address |
|----|--------|------|
| Mac | Finder -> Connect to server... | smb://IOWA;bhe2@lc-rs-storage17.hpc.uiowa.edu/grelab |
| Linux | File manager -> Ctrl+l | smb://IOWA;bhe2@lc-rs-storage17.hpc.uiowa.edu/grelab |
| Windows | [Instructions](https://its.uiowa.edu/support/article/102465) | \\lc-rs-storage17.hpc.uiowa.edu\grelab |

## Command line mount

In Linux / Mac OS, one can use the following command to mount LSS or RDSS

```bash
# LSS
mount -t cifs -o username=bhe2,sec=ntlm,domain=iowa //lc-rs-storage17.hpc.uiowa.edu/grelab /mnt/cifs/lss_grelab
# RDSS
mount -t cifs -o username=bhe2,domain=iowa //rdss.iowa.uiowa.edu/rdss_bhe2 /mnt/cifs/rdss_bhe2 # however, I don't have permission when the drive is mounted this way
```

# How to use LSS server


# FAQ

1. In Linux/Mac OS, is the "map as a folder" the same as "command line mount"? Where are they in the file system?

    They are the same in nature. But when "connect to server" in the GUI is used, the mount point in recent Linux versions (circa 2018, tested in Fedora+MATE and Ubuntu 16.04) is `/run/user/$UID/gvfs/`. When `mount` command is used, the user specifies the mount position. Since these are simply different "portal" for the same windows share, they should be synced.
