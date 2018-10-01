---
title: Installation Guide
author: Tomislav Sirovec      
date: 14/6/2018  
description: This article explains how to install SPDocKit Consultant.
---
This article explains how to install SPDocKit Consultant.

There are few things you need to know, so lets get started.  

__SPDocKit Snapshot Wizard (or the PowerShell Module)__ uses the SharePoint Server Object Model to retrieve information about your farm and it needs to run on the SharePoint server to be able to make API calls. Therefore, the SPDocKit Consultant Snapshot Wizard needs to be run on a server inside of your SharePoint farm. This is a __zero-footprint wizard and there is no installation__.  
[Here](#internal/how-to/create-snapshot) are more information about the snapshot process. 

The application - __SPDocKit Consultant__ must be installed on a workstation with a __Windows 7, Windows 8 or Windows 10__ operating system. You will not be able to load SharePoint farm settings, only open already made snapshots. [Read more about required system settings.](#internal/requirements/system-requirements/)

1. [Download](https://www.syskit.com/products/spdockit/download/) Application.
1. Unpack and run __SPDocKitConsultantSetup.exe.__ The wizard will guide you through the installation steps, click Next > to proceed.
1. Click I Accept the terms of the license agreement to accept the license and then click Next > to proceed.
1. Choose the installation folder e.g. __C:\Program Files\SysKit\SPDocKit Consultant.__ Click __Next__ > to proceed.
1. Select the location where to create application shortcuts and the preferred availability option (__Anyone__ or __Only me__). Click __Next__ > to proceed.
1. The installation wizard will unpack your files and you will be able to run the application from: __Start__ > __All Programs__ > __SPDocKit Consultant.__

## Tips & tricks
If during the installation you encounter any problems and wish to enable logging to help you resolve the problems, you can start the installation using the command prompt with the following argument:
* /l=”full path” will create a log file on a specified location.

For example, if you want to place the log file named __spdockit_installation_log.txt__ in the __temp__ folder on the __C:\\__ drive, the full command will look like this:

`SPDocKitConsultantSetup.exe /l="C:\temp\spdockit_installation_log.txt"`

## Learn more
* [How to: Create Farm Documentation](#internal/how-to/farm-documentation/create-farm-documentation/)
* [How to: Compare SharePoint Farms](#internal/how-to/compare-wizard/compare-sharepoint-farms/)
