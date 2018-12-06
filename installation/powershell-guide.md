---
title: SPDocKit PowerShell Module Install/Uninstall
author: Janko Ban      
date: 4/12/2018  
description: This article explains how to install/uninstall SPDocKit PowerShell Module.
---
This article explains how to install/uninstall SPDocKit PowerShell Module.

SPDocKit PS module is used to collect SharePoint farm settings and permissions. SPDocKit PS module needs to run on a server inside your client’s farm.

After acquiring PowerShell module from [PowerShell Gallery](https://www.powershellgallery.com/packages/SysKit.SPDocKit.PS/) or SysKit [Customers Web](https://my.syskit.com), the module can be imported by manually copying the module and pasting it to the PowerShell module path or by using the <Install – Module> command, whichever you prefer.

The PowerShell module can be used with __PowerShell version 3.0 or higher.__

## 1.	Using the <Install–Module> command: 

To be able to __install__ SPDocKit PS module using PowerShell's __Install-Module__ command, PowerShell 5 is required.

1.	Save the module to preferred location:

```powershell
Save-Module -Name SysKit.SPDocKit.PS -Path < path >
```
< path > can be any location of your choice such as: C:\Users\Public\Desktop

Save–Module command automatically downloads and unzips module to location.

2.	Install the module:

```powershell
Install-Module -Name SysKit.SPDocKit.PS
```
Install-Module command installs SPDocKit PS Module to default location: 
C:\Program Files\WindowsPowerShell\Modules


3.	(Optional) Check the SPDocKit PS module version:

```powershell
Get-SPDocKitVersion
```
Running Get-SPDocKitVersion is used to check SPDocKit PS module version to make sure you have successfully installed the module.

## 2.	Manually copy and paste PowerShell module:

1.	Once you’ve downloaded syskit.spdockit.ps.1.X.X.nupkg, extract the file to a location of your choosing. 

2.	Copy content of syskit.spdockit.ps.1.X.X folder to C:\Program Files\WindowsPowerShell\Modules\SysKit.SPDocKit.PS

If you wish to uninstall SysKit.SPDocKit PS module from a server inside your client’s farm you can use the following command. 

Uninstall the SysKit.SPDocKit PS module:

```powershell
Get-InstalledModule -Name “SysKit.SPDocKit.PS” | Uninstall-Module
```
Or you can manually delete SysKit.SPDocKit PS file from the location you chose during installation. 

SysKit.SPDocKit module update can be done using the following command:

```powershell
Update-Module -Name “SysKit.SPDocKit.PS”
```
__Please note!__ After a successful update of the module, restart of the Windows PowerShell is required before creating the snapshot, otherwise, the snapshot will be created using the old version of the module.

SPDocKit PS module __does not support__ SharePoint 2010.

General information on how to create a snapshot can be viewed [here](#internal/how-to/create-snapshot/).


