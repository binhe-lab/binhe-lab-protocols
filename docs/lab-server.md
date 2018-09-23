---
title: Lab server How-To
author: Bin He
date: 2018-08-26
categories: Basics
tags: bioinfo
---

# Function of lab servers

All data produced in the lab, including raw data and analyses, should be stored on the lab server. The only exception is when the data and analyses are synced to the project [GitHub](https://github.com/binhe-lab) repository. Storing data on the lab servers ensures that data are safe and organized. More importantly, it allows the lab to work together on joint projects. Below are instructions on how to use the lab server.

# How to use the LSS server

Once you join the lab, ask the [Biology IT group](mailto:biology-help-sm@uiowa.edu) to add you to our security group, cc [Bin](mailto:bin-he@uiowa.edu) on your email. It may take a day or two for the security group to be updated so you can access the lab servers. If in doubt, ask Bin.

The lab servers can be accessed by several means:

- Map as a folder on your personal computer
- Mount through the command line on Linux
- Access on HPC (server)
- FTP clients
    
Next we discuss each method separately.

## Map the lab server as a folder

This approach allows you to interact with the lab server as if it were an additional folder on your personal computer.

**Table 1  LSS mounting**

| OS | Menu item | Address |
|----|--------|------|
| Mac | Finder -> Connect to server... | smb://IOWA;**HawkID**@lc-rs-storage17.hpc.uiowa.edu/grelab |
| Windows | [Instructions](https://its.uiowa.edu/support/article/102465) | \\\\lc-rs-storage17.hpc.uiowa.edu\grelab |
| Linux<sup>1</sup> | File manager -> Ctrl+l | smb://IOWA;**HawkID**@lc-rs-storage17.hpc.uiowa.edu/grelab |

- *1 For linux users, the command line usage is preferred*
- *replace "HawkID" with your actual HawkID*
- *Note that if you are off campus, you may need to be connected to the VPN client in order to gain access. Follow the instructions on this [article](https://its.uiowa.edu/support/article/1876)*

## Command line mounting

_Note: If you use one of the lab provided linux desktops, once you log in, use the command line to navigate to `/mnt/nfs/lss_grelab`, and you would have full access to the server space._

If you are using your personal computer running Linux / Mac OS, use the following command to mount LSS

```bash
# LSS
mount -t cifs -o username=HawkID,sec=ntlm,domain=iowa,uid=$(id -u $(whoami)),gid=$(id -g $(whoami)) //lc-rs-storage17.hpc.uiowa.edu/grelab /mnt/cifs/lss_grelab
```

Note that this uses the same CIFS protocol as the previous method (map as a folder). See FAQ below for details.

## Access on HPC

LSS is mounted automatically under `/Shared/grelab`

## FTP

<<<<<<< HEAD
`data.hpc.uiowa.edu` with HawkID and password. The LSS share will be automounted under `/Shared/grelab`
=======
Download a FTP client such as [FileZilla](https://filezilla-project.org/), and point to `data.hpc.uiowa.edu`, login with your HawkID credentials.
>>>>>>> f94fc04133d16a3076630b110e66bced37c4afbb

# FAQ

1. In Linux/Mac OS, is the "map as a folder" the same as "command line mount"? Where are they in the file system?

    The main difference between the two is that the former method uses GVfs (GNOME Virtual file system) as part of the GNU library while the latter uses the `mount` function in the kernel. When "connect to server" in the GUI is used, the mount point in recent Linux versions (circa 2018, tested in Fedora+MATE and Ubuntu 16.04) is `/run/user/$UID/gvfs/`. When `mount` command is used, the user specifies the mount position. Since these are simply different "portal" for the same windows share, they should be synced.

# Appendix: additional servers, overview

There are two major lab servers, provided and managed by different departments at the Information Technology Services. RDSS, standing for Research Data Storage Service, is managed by the [ITS Enterprise Services](https://its.uiowa.edu/about/es). It provides 5TB for free, with 24/7 tech support. It is not accessible, however, on the High Performance Computing clusters. LSS, or Large Storage Service, is offered and managed by the HPC Sysadmins. All UI3 associated labs get 5 TB of LSS storage. Its technical support is business hours only. It is available on the HPC system.

Below is a chart of comparison, also see [here](https://its.uiowa.edu/researchstorage)

**Table 2 Comparison of RDSS and LSSS**

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

**Table 3  RDSS mounting as a folder**

| OS | Menu item | Address |
|----|--------|------|
| Mac | Finder -> Connect to server... | smb://IOWA;HawkID@iowa.uiowa.edu/shared/researchdata/rdss_bhe2 |
| Linux | File manager -> Ctrl+l | smb://IOWA;HawkID@iowa.uiowa.edu/shared/researchdata/rdss_bhe2 |
| Windows | [Instructions](https://its.uiowa.edu/support/article/102465) | \\\\iowa.uiowa.edu\shared\researchdata\rdss_bhe2 |

*replace "HawkID" with your actual HawkID, but don't change the "bhe2"s*

Mount RDSS on Linux using command line:

```bash
# RDSS
mount -t cifs -o username=HawkID,domain=iowa,uid=$(id -u $(whoami)),gid=$(id -g $(whoami)) //rdss.iowa.uiowa.edu/rdss_bhe2 /mnt/cifs/rdss_bhe2 # the additional uid and gid options are required so that the cifs client knows that these are the uid and gid for the user that matches the uid and gid on the server, which can be different.
```
