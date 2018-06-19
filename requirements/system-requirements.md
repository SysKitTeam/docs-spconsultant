---
title: System Requirements
description: This article lists the minimum hardware and software requirements for the installation of the SPDocKit.
author: Tomislav Sirovec
date: 25/6/2018
---
This article lists the minimum hardware and software requirements for SPDocKit. View the corresponding section depending on the scenario you need - either SPDocKit for SharePoint On-Premises or SharePoint Online.

## SharePoint On-Premises


### Requirements

* The product needs to be installed (or started) on a **SharePoint 2016, SharePoint 2013 or SharePoint 2010 Server**
   * For SharePoint 2013 & 2010: SharePoint Foundation, Standard and Enterprise are supported.
   * You can install the product on a WFE (recommended), Application, Index or any other server in the farm.
   * User must have [proper privileges](#internal/requirements/sharepoint-on-premises-user-permissions-requirements/) to run the application.

* Software
  * For SharePoint 2016: Windows 2012 R2 or Windows Server 2016
  * For SharePoint 2013: Windows 2012 or Windows 2008 R2
  * For SharePoint 2010: Windows 2012 or Windows 2008 
  * On Windows 2008 you will need to download [Windows PowerShell Snap-In 1.0](http://www.iis.net/download/powershell) to fully extract information about IIS Settings
  * SQL 2008 or better is supported
  * __Microsoft .NET Framework 3.5 SP1__ for SharePoint 2010, __Microsoft .NET Framework 4.5__ for SharePoint 2013 and SharePoint 2016.

* Hardware
  * CPU – any standard server CPU
  * Memory – up to 200 MB RAM while idle, up to 1GB RAM during the data load
  * Disk – 200 MB disk space
  
### Running on a workstation

The application can be installed on a workstation with __Windows 10, Windows 8 or Windows 7__ 64-bit operating system, but you will not be able to load new SharePoint farm settings, only connect to an existing SPDocKit database and open already saved farm settings.

From version 5.2., SPDocKit installed on a workstation also supports connecting to any __SharePoint 2010, SharePoint 2013, SharePoint 2016__ site and real-time viewing and management of permissions. 

* Hardware:
  * CPU – any Windows 7, Windows 8 or Windows 10 capable CPU
  * Memory – up to 200 MB RAM while idle
  * Disk – 100 MB disk space



User must have [proper privileges](#internal/requirements/sharepoint-online-user-permissions-requirements/) to run the application.

### Learn more
* [Installation Guide](#internal/installation/installation-guide)
* [How to create farm documentation](#internal/how-to/farm-documentation/create-farm-documentation)
* [How to compare SharePoint farms](#internal/how-to/compare-wizard/compare-sharepoint-farms)
