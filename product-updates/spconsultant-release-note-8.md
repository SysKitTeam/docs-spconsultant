---
title: SPDocKit Consultant 8 - Release Note
description: This article describes the new features, improvements, and bug fixes that are delivered in SPDocKit Consultant 8. 
author: Tomislav Sirovec
date: 10/10/2018
---

SPDocKit Consultant comes as a new product with revamped architecture which simplifies consultants’ day to day operations when working with clients. The new approach helps you to take care of your clients’ farms more efficiently! We simplified the collection of data and SharePoint farm settings. As a highly requested feature, we removed the need to install any software on your client's farm servers, so there is no need to install or activate any product in your client’s environment anymore. To create snapshots use the zero-footprint executable __SPDocKit Snapshot Wizard - Consultant__ or the new __[SPDocKit Powershell module](https://www.powershellgallery.com/packages/SysKit.SPDocKit.PS)__ if you prefer to use PowerShell. More information on how the new product works available [here](#internal/how-to/create-snapshot).

Features above are designed to avoid leaving any trace and files in your client's environment.

Give it a try and let us know what you think! 

__Product version:__ 8.0.2 

__Build number:__ ????? 

__Release date:__ Oct 18, 2018 

[Click here to download the new release.](https://www.syskit.com/products/spdockit/download/)


## Features

* __PS Module__ and __SPDocKit Consultant Snapshot Wizard__ - As already mentioned above, these are the two ways of creating a snapshot. There is no need to install or activate any product in your client’s environment anymore. For more information on how to create a snapshot, see [this article.](#internal/how-to/create-snapshot)


* __New XLSX export__ introduced to SPDocKit that comes with an inbuilt functionality to sort and filter data in each column! It is available on all reports, subscriptions and compare results. The old export style available under a different name – Legacy Export as XLSX.

* __SharePoint 2019 supported!__ SPDocKit has been tested on the latest SharePoint 2019 environments. All features are working flawlessly. Try it out yourself!

## Improvements

* __Improved category navigation!__ It is positioned on the left side of the main window and can be collapsed to create even more space for the reports.

* __Farm name is now automatically set__ based on the snapshot data, if available. Otherwise, the usual naming is used - Farm 1, Farm 2, etc. The '#' symbol is no longer a part of this naming since it caused problems when used with cloud-based services.

* __Enable Usage and Health Data Collection report renamed to Usage and Health Data Collection Enabled__, and status of __two additional timer jobs added__ (Microsoft SharePoint Foundation Usage Data Processing and Microsoft SharePoint Foundation Usage Data Import).

* __TempDB Files__ Best Practice report now checks if the tempDB files are on a separate drive from Binaries, Data and Log Files, however, all of the tempDB files can be on the same drive - for more information consult the following [link](https://docs.syskit.com/bp/v1/databases/tempdb/files/). 

* __Content Database Capacity__ Best Practice report now __shows Data File Free Space column instead of Data File Full__.

* __IIS Instance ID column added__ to the __IIS Sites report__.

* Added the text ‘[MB]’ to headers of Storage Maximum Level, Storage Warning Level, and Usage Storage columns on the __Site Collection Quotas report__ to clarify which measurement units are displayed.

* __Snapshot filter can now be extended__ in which case it shows the information about load depth, snapshot mode, and if a snapshot is marked as good configuration.

* The __latest snapshot is now automatically opened__ when viewing Farm Explorer and Best Practices reports. The ‘Reopen last accessed snapshot on start up’ option was, therefore, removed from SPDocKit Options. 

* The __details of inner exceptions are now displayed__ if they occur while taking a snapshot to make the troubleshooting easier.

* __Multiple Export buttons replaced with one Export button__. Default export type is set to XLSX, with an available dropdown option where you can select a different export type. 

* Servers in the __Browse for Servers list__ in the Configuration Wizard is now __alphabetically ordered__, for you to quickly find the server you need.


## Bug Fixes

* Fixed a bug where special characters in a report name could cause an error when exporting to excel file. 

* Fixed a bug where the Source and Target rows of the Compare Results window were of sync when the horizontal scroll was visible.

* Fixed a bug where a wrong total number of site collections was displayed on the Snapshot Wizard while taking a snapshot on the SharePoint 2016 environment.

* Fixed an issue where the Best Practice Wizard would result in a smart error when a DateTime type of column was selected on the Conditional Formatting step.

* Fixed a bug where changing between Farm Explorer and Best Practices reports caused the app to crash on multifarm environments. 

* Fixed an issue where you could change steps on the Finish step of the Configuration Wizard which resulted in an error. 

* Fixed a bug where AutoSPInstaller would cause a cast exception: ‘Unable to cast object of type 'System.DBNull' to type 'System.String'.’

* Fixed an issue where the License Details form didn’t display the Name and Email values.

* Fixed a rare bug in various BP reports where filtering the underlying data for the report would cause a Syntax error exception.

* Fixed an issue where the Incremental Search BP report didn’t show an error, although the setting was not in the defined range.  


## Deprecated Features

* __SPDocKit run mode__ has been replaced with new apps used with SPDocKit Consultant.
For more information visit the [following link](#internal/how-to/create-snapshot).

* The __XML File__ option for saving snapshots has been removed.