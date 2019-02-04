---
title: Upgrade to the Latest Version
author: Tomislav Sirovec
date: 20/6/2018
description: This article explains how to upgrade SPDocKit Consultant to the latest major version.
---

# Upgrade to the Latest Version

## Instructions

1. Download the latest SPDocKit Consultant version and run the **SPDocKitConsultantSetup.exe**.
2. If a previous SPDocKit Consultant version is already installed, the **Installation Wizard** will inform you that it will be **uninstalled automatically**.
3. Click **I Accept the terms of the license agreement** to accept the license and then click **Next** &gt; to proceed.
4. Choose the installation folder e.g. **C:\Program Files\SysKit\SPDocKit Consultant**. Click **Next** &gt; to proceed.
5. Select the location where to create application shortcuts and the preferred availability option \(**Anyone** or **Only me**\). Click **Next** &gt; to proceed.
6. The installation wizard will unpack your files and you will be able to run the application from: **Start** &gt; **All Programs** &gt; **SPDocKit Consultant.**

## Tips & tricks

If during the installation you encounter any problems and wish to enable logging to help you resolve the problems, you can start the installation using the command prompt with the following argument:

* /l=”full path” will create a log file on a specified location.

For example, if you want to place the log file named **spdockit\_installation\_log.txt** in the **temp** folder on the **C:\** drive, the full command will look like this:

`SPDocKitConsultantSetup.exe /l="C:\temp\spdockit_installation_log.txt"`

