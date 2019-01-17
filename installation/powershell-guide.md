---
title: SPDocKit PowerShell Module Install/Uninstall
author: Janko Ban
date: 4/12/2018
description: This article explains how to install/uninstall SPDocKit PowerShell Module.
---

# PowerShell Guide

SPDocKit PS module is used to collect SharePoint farm settings and permissions. SPDocKit PS module needs to run on a server inside your client’s farm.

After acquiring PowerShell module from [PowerShell Gallery](https://www.powershellgallery.com/packages/SysKit.SPDocKit.PS/) or SysKit [Customers Web](https://my.syskit.com), the module can be imported by manually copying the module and pasting it to the PowerShell module path or by using the command, whichever you prefer.

The PowerShell module can be used with **PowerShell version 3.0 or higher.**

## 1.    Using the  command:

To be able to **install** SPDocKit PS module using PowerShell's **Install-Module** command, PowerShell 5 is required.

1. Save the module to preferred location:

```text
Save-Module -Name SysKit.SPDocKit.PS -Path < path >
```

&lt; path &gt; can be any location of your choice such as: C:\Users\Public\Desktop

Save–Module command automatically downloads and unzips module to location.

1. Install the module:

```text
Install-Module -Name SysKit.SPDocKit.PS
```

Install-Module command installs SPDocKit PS Module to default location: C:\Program Files\WindowsPowerShell\Modules

1. \(Optional\) Check the SPDocKit PS module version:

```text
Get-SPDocKitVersion
```

Running Get-SPDocKitVersion is used to check SPDocKit PS module version to make sure you have successfully installed the module.

## 2.    Manually copy and paste PowerShell module:

1. Once you’ve downloaded syskit.spdockit.ps.1.X.X.nupkg, extract the file to a location of your choosing.
2. Copy content of syskit.spdockit.ps.1.X.X folder to C:\Program Files\WindowsPowerShell\Modules\SysKit.SPDocKit.PS

If you wish to uninstall SysKit.SPDocKit PS module from a server inside your client’s farm you can use the following command.

Uninstall the SysKit.SPDocKit PS module:

```text
Get-InstalledModule -Name “SysKit.SPDocKit.PS” | Uninstall-Module
```

Or you can manually delete SysKit.SPDocKit PS file from the location you chose during installation.

SysKit.SPDocKit module update can be done using the following command:

```text
Update-Module -Name “SysKit.SPDocKit.PS”
```

{% hint style="warning" %}
**Please note!** After a successful update of the module, restart of the Windows PowerShell is required before creating the snapshot, otherwise, the snapshot will be created using the old version of the module.
{% endhint %}

SPDocKit PS module **does not support** SharePoint 2010.

General information on how to create a snapshot can be viewed [here](../how-to/create-snapshot.md).

