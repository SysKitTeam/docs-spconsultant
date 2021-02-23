---
description: This article explains how to install SPDocKit Consultant.
---

# Installation Guide

## Client Farm

**SPDocKit Snapshot Wizard \(or the PowerShell Module\)** uses the SharePoint Server Object Model to retrieve information about your farm and it needs to run on the SharePoint server to be able to make API calls. Therefore, the SPDocKit Consultant Snapshot Wizard needs to be run on a server inside your client's farm. This is a **zero-footprint wizard and there is no installation**.  
[Here](../how-to/create-snapshot.md) are more information about the snapshot process.

## Consultant Workstation

The application - **SPDocKit Consultant** must be installed on a **consultants workstation**, and not at your client as you can activate it only once. You only open already saved farm settings. [Read more about required system settings.](../requirements/system-requirements.md)

1. [Download](https://www.syskit.com/products/spdockit/download/) Application.
2. Unpack and run **SPDocKitConsultantSetup.exe.** The wizard will guide you through the installation steps, click Next &gt; to proceed.
3. Click I Accept the terms of the license agreement to accept the license and then click Next &gt; to proceed.
4. Choose the installation folder e.g. **C:\Program Files\SysKit\SPDocKit Consultant.** Click **Next** &gt; to proceed.
5. Select the location where to create application shortcuts and the preferred availability option \(**Anyone** or **Only me**\). Click **Next** &gt; to proceed.
6. The installation wizard will unpack your files and you will be able to run the application from: **Start** &gt; **All Programs** &gt; **SPDocKit Consultant.**

## Tips & tricks

If during the installation you encounter any problems and wish to enable logging to help you resolve the problems, you can start the installation using the command prompt with the following argument:

* /l=”full path” will create a log file on a specified location.

For example, if you want to place the log file named **spdockit\_installation\_log.txt** in the **temp** folder on the **C:\** drive, the full command will look like this:

`SPDocKitConsultantSetup.exe /l="C:\temp\spdockit_installation_log.txt"`

## Learn more

* [How to: Create Farm Documentation](../how-to/farm-documentation/create-farm-documentation.md)
* [How to: Compare SharePoint Farms](../how-to/compare-wizard/compare-sharepoint-farms.md)

