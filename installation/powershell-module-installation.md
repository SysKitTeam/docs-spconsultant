---
title: SPDocKit PowerShell Module Install/Uninstall
author: Janko Ban      
date: 4/12/2018  
description: This article explains how to install SPDocKit PowerShell Module.
---
This article explains how to install/uninstall SPDocKit PowerShell Module.

SPDocKit PS module is used to collect SharePoint farm settings and permissions. SPDocKit PS module needs to run on a server inside your client’s farm.

After acquiring PowerShell module from [PowerShell Gallery](https://www.powershellgallery.com/packages/SysKit.SPDocKit.PS/) or SysKit [Customers Web](https://my.syskit.com), module can be imported by manually copying the module and pasting it to the PowerShell module path or by using the <Install – Module> command, whichever you prefer.

The PowerShell module can be used with __PowerShell version 3.0 or higher.__

To be able to install SPDocKit PS module using PowerShell, PowerShell 5 is required.

## 1.	Using the <Install–Module> command: 

1.	Save the module to preferred location:

```powershell
Save-Module -Name SysKit.PS -Path < path >
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

1.	Once you’ve downloaded syskit.spdockit.ps.1.0.X.nupkg, extract the file to location of your choosing. 

2.	Copy syskit.spdockit.ps.1.0.X folder to C:\Program Files\WindowsPowerShell\Modules

If you wish to uninstall SysKit.SPDocKit PS module from server inside your client’s farm you can use the following command. 

Uninstall the SysKit.SPDocKit PS module:

```powershell
Get-Installed-Module -Name “SysKit.SPDocKit.PS” | Uninstall-Module
```
Or you can manually delete SysKit.SPDocKit PS file from location you chose during installation. 

SysKit.SPDocKit module update can be done using following command:

Update the SysKit.SPDocKit PS module:

```powershell
Update-Module -Name “SysKit.SPDocKit.PS”
```
General information on how to create a snapshot can be viewed [here](#internal/how-to/create-snapshot/).


