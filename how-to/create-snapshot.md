---
title: Create a snapshot using the SPDocKit Consultant
description: This section describes how to create a snapshot using the SPDocKit Consultant. 
author: Tomislav Sirovec
date: 19/6/2018
---

This section describes how you can use SPDocKit Snapshot Wizard - Consultant or the PowerShell module to collect SharePoint farm settings and permissions.
Please note! Adjustments and settings you make when using SPDocKit Snapshot Wizard - Consultant will be saved and used the next time you run it.
The PowerShell module has no such abilities. However, you can copy and save your favorite command with a defined set of parameters in a text file and copy-paste it to PowerShell the next time you want to create a snapshot.

## SPDocKit Snapshot Wizard - Consultant

SPDocKit Snapshot Wizard - Consultant files can be found in the installation folder of SPDocKit Consultant on your workstation.
To easily locate it, open SPDocKit Consultant and click the __Take Snapshot__ button on the Backstage screen. An info window on how to take a snapshot appears. 
Click the __Quick Open__ button - folder containing the SPDocKit Snapshot Wizard - Consultant is opened and the .zip file is selected. 

Copy the preselected archive to the SharePoint server where you want to take a snapshot and extract the contents.
Locate the __SPDocKitSnapshotWizard.exe__ among the extracted files and run it - the SPDocKit Snapshot Wizard - Consultant opens. 

__Note:__ When creating a snapshot on clients' farm you want to leave minimal or no traces behind you. With the SPDocKit Snapshot Wizard - Consultant there are no files left behind since the installation is not required. 

Let's take a closer look at the steps and the options available:

#### Welcome
  * __Snapshot Location__ - Define where to save the snapshot file after the load is completed. By default, the snapshots will be placed in the __Snapshots__ folder in the same location as the SPDocKit Snapshot Wizard - Consultant .exe file. 
  * __Verbose Logging__ - Check this option for a more detailed logging when troubleshooting.

#### Load Options

  * __Load Depth__ - Specify the depth to which you want to crawl your farm. You can choose between Web Applications and Site Collections. 
   
  * __SharePoint__
    * __Farm Settings__ - Farm settings are loaded by default and this option cannot be changed. 
    * __Features and Solutions__
    * __Workflows__

  * __Security__ 
    * __Database Permissions__ - Check this option to view the Database Permissions report. This report shows information about all users, across all databases on a SQL Server. 

  * __Server Settings__ 
    * __Installed Programs and available Updates__
    * __SQL Server Information__
    * __IIS Settings Information__

  * __Project Server__ 
    * __Settings__
    * __Projects__  

   To reduce the farm load time we recommend unchecking Personal Sites. You can use the load performance slider to switch between low resource usage and a high-performance load.

#### Target
You can choose your target to be the entire farm, Web application or specific site collection.
Click Next and the loading will start.

#### Loading Progress  
Shows the current loading progress. When the load is finished, it is possible to save the loading log by clicking the __Save Log__ button.

#### Finish
The last step enables you to easily navigate to the created snapshot by clicking the __Open Snapshot Location__ button. 

The snapshot can now be copied to the workstation and imported with SPDocKit Consultant for further analysis.

## SPDocKit PowerShell Module

The SysKit.SPDocKit.PS PowerShell module can be aquired from [PowerShell Gallery](https://www.powershellgallery.com/packages/SysKit.SPDocKit.PS/) or [SysKit Customers Web](https://my.syskit.com).

Once you've downloaded the __SysKit.SPDocKit.PS.zip__ file, extract the contents to __SysKit.SPDocKit.PS__ folder.
The folder should then be copied to one of the default PowerShell module paths. You can easily discover them by running the following command in PowerShell:

```powershell
$env:PSModulePath -split ';'
```

Now copy the __SysKit.SPDocKit.PS__ folder to one of the displayed paths. 

First, let's check the __SysKit.SPDocKit.PS__ module version. Type the following command into PowerShell:

```powershell
Get-SPDocKitVersion
```

To create a snapshot with the __SysKit.SPDocKit.PS__ module, the following command is used:
```powershell
New-SPDocKitSnapshot
```
The load starts and the current Loading Target is displayed in the progress bar.

To find all about the __New-SPDocKitSnapshot__ command use the following command:

```powershell
Get-Help New-SPDocKitSnapshot -full
```

[//]: # (TODO - provjeriti ovaj link za online dokumentaciju kada se ona postavi online)

The documentation is also available for you to view [online](https://www.powershellgallery.com/Errors/404?aspxerrorpath=/packages/SysKit.SPDocKit.PS/1.0.1/Documentation)
