---
description: This article lists the minimum hardware and software requirements for the installation of SPDocKit Consultant.
---

# System Requirements

## Client Farm Requirements

* The product **\(SPDocKit Snapshot Wizard or the PowerShell Module\)** needs to be started on a **SharePoint 2019, SharePoint 2016, SharePoint 2013 or SharePoint 2010 Server**
  * For SharePoint 2013 & 2010: SharePoint Foundation, Standard and Enterprise are supported.
  * You can run the product on a WFE \(recommended\), Application, Index or any other server in the farm.
  * User must have [proper privileges](user-permission-requirements.md) to perform the snapshot process. 
* Software
  * For SharePoint 2019: Windows Server 2012 R2, Windows Server 2016, or Windows Server 2019
  * For SharePoint 2016: Windows Server 2012 R2, Windows Server 2016, or Windows Server 2019
  * For SharePoint 2013: Windows Server 2012 or Windows Server 2008 R2
  * For SharePoint 2010: Windows Server 2012 or Windows Server 2008 
  * On Windows Server 2008 you will need to download [Windows PowerShell Snap-In 1.0](http://www.iis.net/download/powershell) to fully extract information about IIS Settings
  * **Microsoft .NET Framework 3.5 SP1** for SharePoint 2010, **Microsoft .NET Framework 4.5** for SharePoint 2013 and SharePoint 2016.
* Hardware
  * CPU – any standard server CPU
  * Memory – up to 200 MB RAM while idle, up to 1GB RAM during the data load
  * Disk – 200 MB disk space

## Consultant Workstation Requirements

The application - **SPDocKit Consultant** must be installed on a **consultants workstation**, and not at your client as you can activate it only once. You can only open already saved farm settings.

{% hint style="warning" %}
**Please note!**  
**SPDocKit Consultant** is not meant to be installed on a SharePoint server, but to serve as a hub. A managing place for all the snapshots you create on your client's farms.
{% endhint %}

* Hardware:
  * CPU – any Windows 7, Windows 8 or Windows 10 capable CPU
  * Memory – up to 200 MB RAM while idle
  * Disk – 100 MB disk space

### Learn more

* [Installation Guide](../installation/installation-guide.md)
* [How to create farm documentation](../how-to/farm-documentation/create-farm-documentation.md)
* [How to compare SharePoint farms](../how-to/compare-wizard/compare-sharepoint-farms.md)

