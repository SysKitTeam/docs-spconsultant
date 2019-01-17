---
title: Create a snapshot using the SPDocKit Consultant
description: This section describes how to create a snapshot using the SPDocKit Consultant.
author: Tomislav Sirovec
date: 19/6/2018
---

# create-snapshot

This section describes how you can use SPDocKit Snapshot Wizard - Consultant or the PowerShell module to collect SharePoint farm settings and permissions.

There are two ways to create a snapshot of the selected farm \(both need to be run on the selected farm\).

## 1. SPDocKit Snapshot Wizard - Consultant

SPDocKit Snapshot Wizard - Consultant files can be found in the installation folder of SPDocKit Consultant or downloaded from [SysKit Customers Web](https://my.syskit.com). To easily locate the installation folder, open SPDocKit Consultant and click the **Take Snapshot** button on the Backstage screen. An info window on how to take a snapshot appears. Click the **Quick Open** button. A folder containing the SPDocKit Snapshot Wizard - Consultant is opened and the .zip file is selected.

Copy the preselected archive to the SharePoint server where you want to take a snapshot and extract the contents. Locate the **SPDocKitSnapshotWizard.exe** among the extracted files and run it. The **SPDocKit Snapshot Wizard - Consultant** opens.

**Note:** When creating a snapshot on a clients' farm, you want to leave minimal or no traces behind you. When you use the SPDocKit Snapshot Wizard - Consultant, there are **no files left behind** since installation is not required.

Let's take a closer look at the steps and the options available:

#### Welcome

* **Snapshot Location** - Define where to save the snapshot file after the load is completed. By default, the snapshots will be placed in the **Snapshots** folder, in the same location as the SPDocKit Snapshot Wizard - Consultant .exe file. 
* **Verbose Logging** - Check this option for more detailed logging when troubleshooting.

#### Load Options

* **Load Depth** - Specify the depth to which you want to crawl your farm. You can choose between Web Applications and Site Collections.
* **SharePoint**
  * **Farm Settings** - Farm settings are loaded by default. This option cannot be changed. 
  * **Features and Solutions**
  * **Workflows**
* **Security**
  * **Database Permissions** - Check this option to view the Database Permissions report. This report shows information about all users, across all databases on a SQL Server. 
* **Server Settings**
  * **Installed Programs and available Updates**
  * **SQL Server Information**
  * **IIS Settings Information**
* **Project Server**

  * **Settings**
  * **Projects**  

  To reduce the farm load time we recommend unchecking Personal Sites. You can use the load performance slider to switch between low resource usage and a high-performance load.

#### Target

You can choose your target to be the entire farm, Web application, or specific site collection. Click Next and the loading will start.

#### Loading Progress

Shows the current loading progress. When the load is finished, you can save the loading log by clicking the **Save Log** button.

#### Finish

The last step enables you to easily navigate to the created snapshot by clicking the **Open Snapshot Location** button.

The snapshot can now be copied to the workstation and imported with SPDocKit Consultant for further analysis.

## 2. SPDocKit PowerShell Module

Instructions on how to install SPDocKit PowerShell Module can be found [here](../installation/powershell-guide.md).

### Creating a snapshot:

To create a snapshot with the **SysKit.SPDocKit.PS** module, use the following command:

```text
New-SPDocKitSnapshot
```

The load starts and the current Loading Target is displayed in the progress bar.

To find out all about the **New-SPDocKitSnapshot** command, use the following command:

```text
Get-Help New-SPDocKitSnapshot -full
```

The documentation is also available [here](../get-to-know-spdockit/powershell-commands.md).

**Please note!**

* The PowerShell module can be used with **PowerShell version 3.0 or higher.** To create a snapshot in such environments, please use **SPDocKit Snapshot Wizard - Consultant.**
* It is not possible to create a snapshot of SharePoint 2010 using the PowerShell.
* Any adjustments and settings you make when using SPDocKit Snapshot Wizard - Consultant will be saved and used the next time you run it.

  The PowerShell module has no such abilities. However, you can copy and save your favorite command with a defined set of parameters in a text file and copy and paste it to PowerShell the next time you want to create a snapshot.

