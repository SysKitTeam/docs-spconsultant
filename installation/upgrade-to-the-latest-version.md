---
title: Upgrade to the Latest Version
author: Tomislav Sirovec      
date: 20/6/2018
description: This article explains how to upgrade SPDocKit to the latest major version.
---

This article explains how to upgrade SPDocKit to the latest major version. Snapshots and application settings will be preserved in the upgrade process.

## Instructions
1. Download the latest SPDocKit version and run the __SPDocKitConsultantSetup.exe__.
2. If a previous SPDocKit Consultant version is already installed, the __Installation Wizard__ will inform you that it will be __uninstalled automatically__.
3. Click __I Accept the terms of the license agreement__ to accept the license and then click __Next__ > to proceed.
4. Choose the installation folder e.g. __C:\Program Files\SysKit\SPDocKit Consultant__. Click __Next__ > to proceed.
5. Select the location where to create application shortcuts and the preferred availability option (__Anyone__ or __Only me__). Click __Next__ > to proceed.
6. The installation wizard will unpack your files and you will be able to run the application from: __Start__ > __All Programs__ > __SPDocKit Consultant.__

## Tips & tricks
If during the installation you encounter any problems and wish to enable logging to help you resolve the problems, you can start the installation using the command prompt with the following argument:
* /l=”full path” will create a log file on a specified location.

For example, if you want to place the log file named __spdockit_installation_log.txt__ in the __temp__ folder on the __C:\\__ drive, the full command will look like this:

`SPDocKitConsultantSetup.exe /l="C:\temp\spdockit_installation_log.txt"`
