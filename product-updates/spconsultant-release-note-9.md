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

  Get the most important information at a glance with a new visually appealing dashboard. Each dashboard tile enables you to drill down to a more detailed report where you can find specific information of interest. Find more about the **Farm dashboard** here. 

* **New Server Differences alerts available!**

  While comparing servers, you can now easily create a Server Differences alert that will be sent to you after each automatic snapshot. You can compare SQL, IIS, and all farm servers in general.

## Improvements

* **SPDocKit service improved!** Since adding a couple of new system jobs to SPDocKit, we have tweaked the underlying service that runs them. Now, after each automatic snapshot, the service restarts and frees the memory from unused resources. The job schedule was also improved, to ensure faster job execution and prevent possible locks when multiple jobs are running simultaneously.
* **Database Disk Usage**, **Database Size Growth**, and **Logs Size Growth** reports are now **combined into a single report**: the **Database Growth** report. The new design enables you to more easily find the information you want, and track database growth over time. The revamped report now uses data collected by the **new Database Analytics system job** and has, therefore, become faster.
* **Improved Data retention!**  It is now possible to define **separate data retention settings exclusively for audit logs and administrative actions** – just in case you want to hang on to your audit logs a bit longer. You can now view the progress when manually running data retention, and cancel the execution if you need to.
* **Improved Farm Compare!**  Because some Windows services often change state between “stopped” and “running,” a newly created snapshot would often show a difference between itself and the previous snapshot. In order to reduce the number of false negatives, the following services are no longer considered in compare: **WinHTTP Web Proxy Auto-Discovery Service, Network Setup Service, Microsoft Passport, Application Experience, WMI Performance Adapter.**
* **SharePoint Analytics** report **renamed Site Collection Analytics**.  The Active Subsites column was added to provide you with even more useful information about your site collection usage.
* Site collection **search functionality enabled in Storage Metrics** report.  When a match is found for the entered term, the parent object of the site collection is expanded, and the site collection itself is highlighted.
* **We retired the Content Overview** report and replaced it with the new, better, and faster **Analytics Dashboard**.
* **Last Modified By information added** to Inactive Subsites and Unmodified Lists Analytics reports.
* **Actions filter added** to the Administrative Actions report.
* **Site Visitors List** report **renamed Site Collection Visitors**, and the date range filter limited to 30 days.
* **Added search** in the Actions filter on Administrative Actions report.
* **Improved UX** when creating a snapshot with SPDocKit PowerShell module. On snapshot completion, the snapshot’s parent folder is opened and the snapshot file is automatically selected.
* **Numerous UI improvements**: clearer wizard descriptions; humanized error messages; improved behavior of filters; improved refresh of reports; data source info added to status bar, etc.
* **Expand All Groups button disabled** in Storage Metrics report. Since this action is costly in resources, it was disabled.

## Bug Fixes

* Fixed a bug where the System Account was displayed as Unknown in the Audit Log Details report.
* Fixed a bug where querying recursive AD groups would cause a memory bottleneck and consequently performance problems with the SQL server.
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
* Consultant: Fixed a bug where the app would crash when trying to import a snapshot with the lower case extension ‘spdfarmx’ instead of the regular ‘SPDFarmx’ version. The import now supports both options.
* Fixed a bug where the mouse wheel scroll would not work on the Document Extension Overview report.

