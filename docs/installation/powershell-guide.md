---
sidebar_position: 4
description: >-
  This article explains how to install, uninstall, or update SPDocKit PowerShell
  Module.
---

# PowerShell Guide

SPDocKit PS module is used to collect SharePoint farm settings and permissions. SPDocKit PS module needs to run on a server inside your client’s farm.

After acquiring PowerShell module from [PowerShell Gallery](https://www.powershellgallery.com/packages/SysKit.SPDocKit.PS/) or Syskit [Customers Web](https://my.syskit.com), the module can be imported by manually copying the module and pasting it to the PowerShell module path or by using the command, whichever you prefer.

The PowerShell module can be used with **PowerShell version 3.0 or higher.**

## Install SPDocKit PowerShell Module

### 1. Using the command

:::warning
**Please note!**\
To be able to install SPDocKit PS module using PowerShell's Install-Module command, PowerShell 5 or later is required.

You can easily upgrade PowerShell by downloading [WMF 5.0 or later.](https://www.microsoft.com/en-us/download/details.aspx?id=54616)
:::

* Save the module to preferred location:

```powershell
Save-Module -Name SysKit.SPDocKit.PS -Path < path >
```

< path > can be any location of your choice such as: C:\Users\Public\Desktop\
Save–Module command automatically downloads and unzips module to location.

* Install the module:

```powershell
Install-Module -Name SysKit.SPDocKit.PS
```

Install-Module command installs SPDocKit PS Module to default location: C:\Program Files\WindowsPowerShell\Modules

* (Optional) Check the SPDocKit PS module version:

```powershell
Get-SPDocKitVersion
```

Running Get-SPDocKitVersion is used to check SPDocKit PS module version to make sure you have successfully installed the module.

### 2. Manually copy and paste PowerShell module:

* Go to [PowerShell Gallery](https://www.powershellgallery.com/packages/SysKit.SPDocKit.PS/) to find the latest version of SPDocKit PowerShell module.
* Navigate to the **Manual Download** tab, then select the **Download the raw nupkg file** option.
* Once you’ve downloaded **syskit.spdockit.ps.1.X.X.nupkg**, change the file extension from .nupkg to .zip and extract it to a location of your choosing.

:::warning
**Please note!**\
The file you downloaded is just a .zip archive with extra files containing information about the contents of the package. You can unpack the downloaded file by changing the file extension from .nupkg to .zip.
:::

* Finally, copy the extracted content from syskit.spdockit.ps.1.X.X folder to **C:\Program Files\WindowsPowerShell\Modules\SysKit.SPDocKit.PS.**

## Uninstall SPDocKit PowerShell Module

If you wish to uninstall SysKit.SPDocKit PS module from a server inside your client’s farm you can use the following command:

```powershell
Get-InstalledModule -Name “SysKit.SPDocKit.PS” | Uninstall-Module
```

Or you can manually delete SysKit.SPDocKit PS file from the location you chose during installation.

## Update SPDocKit PowerShell Module

SysKit.SPDocKit module update can be done using the following command:

```powershell
Update-Module -Name “SysKit.SPDocKit.PS”
```

To update the module manually, first, uninstall the existing version of module, then follow instructions in **[section 2](powershell-guide.md#2-manually-copy-and-paste-powershell-module)** of this article.

:::warning
**Please note!**\
After a successful update of the module, restart of the Windows PowerShell is required before creating the snapshot, otherwise, the snapshot will be created using the old version of the module.
:::

:::warning
SPDocKit PS module **does not support** SharePoint 2010.
:::

General information on how to create a snapshot can be viewed [here](../how-to/create-snapshot.md).

