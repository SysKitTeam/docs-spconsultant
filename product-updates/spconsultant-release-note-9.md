---
title: SPDocKit Consultant 9 — Release Note
description: >-
  This article describes the new features, improvements, and bug fixes that are
  delivered in SPDocKit Consultant 9.
author: Igor Mesaric
date: 05/02/2018
---

# SPDocKit Consultant 9

**SPDocKit Consultant 9** is a major release that comes with a new dashboard, and other neat things. The list is long, so, let's get to it!

**Product version:** 9.0.0  
**Build number:** 10941  
**Release date:** Feb 05, 2019

[Click here to download the new release.](https://www.syskit.com/products/spdockit/download/)

## Features

* **Introducing the new Farm Dashboard!**

  Get the most important information at a glance with a new visually appealing dashboard. Each dashboard tile enables you to drill down to a more detailed report where you can find specific information of interest. Find more about the **Farm dashboard** [here](../get-to-know-spdockit/farm-explorer-screen/farm-dashboard.md). 

* **New Server Differences alerts available!**

  While comparing servers, you can now easily create a Server Differences alert that will be sent to you after each automatic snapshot. You can compare SQL, IIS, and all farm servers in general.

## Improvements

* **Actions filter added** to the Administrative Actions report.
* **Site Visitors List** report **renamed Site Collection Visitors**, and the date range filter limited to 30 days.
* **Added search** in the Actions filter on Administrative Actions report.
* **Improved UX** when creating a snapshot with SPDocKit PowerShell module. On snapshot completion, the snapshot’s parent folder is opened and the snapshot file is automatically selected.
* **Numerous UI improvements**: clearer wizard descriptions; humanized error messages; improved behavior of filters; improved refresh of reports; data source info added to status bar, etc.
* **Expand All Groups button disabled** in Storage Metrics report. Since this action is costly in resources, it was disabled.

## Bug Fixes

* Fixed an issue where the Disk Allocation Size and Database Files reports showed no data for servers with Always On Availability Groups configured.
* Fixed a bug where the Storage Metrics report would erroneously handle and show data for content databases from different farms with the same name.
* Fixed an issue where the Permissions Matrix report failed to show AD groups nested inside SharePoint Groups when the Principal Types filter was set to Active Directory Groups only.
* Fixed an issue where differences were falsely indicated when comparing Service Applications Administrators.
* Fixed a bug where the Include Content filter showed No Data when creating a Permission Differences alert. The default selection is now set to include all content and the filter itself is no longer visible in the wizard.
* Fixed a bug in the Restore Permissions wizard that prevented the restore action being performed on the AD group ‘Everyone’. The following error was thrown: System.IndexOutOfRangeException: Index was outside the bounds of the array.
* Fixed an issue where the System Data would show a negative size in the Storage Metrics report.
* Fixed an issue where the Site Collection label was unnecessarily displayed in the export of Audit Settings and Audit Log Details reports.
* Fixed an issue where the snapshot backup files were visible when browsing snapshot files to open in SPDocKit.
* Fixed an issue where the Date range filter information was erroneously exported.
* Fixed a bug where the Extension filter selection was not shown in the exported Document Extension Details report.
* Fixed a bug with Farm Differences Subscription on SharePoint 2010 Farms. When sending a subscription, the following error would appear: System.NotSupportedException: Unable to create a constant value of type 'Acceleratio.SPDocKit.UserControls.PrintContainer.
* Fixed a bug where the app would crash when trying to create a subscription on a farm for which no snapshots had been created.
* Fixed a bug where the app would crash when trying to import a snapshot with the lower case extension ‘spdfarmx’ instead of the regular ‘SPDFarmx’ version. The import now supports both options.



