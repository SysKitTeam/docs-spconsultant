---
title: SPDocKit Consultant 8 — Release Note
description: This article describes the new features, improvements, and bug fixes that are delivered in SPDocKit Consultant 8. 
author: Tomislav Sirovec
date: 10/10/2018
---

SPDocKit Consultant comes as a new product with revamped architecture that simplifies consultants’ day-to-day operations when working with clients. The new approach helps you to take care of your clients’ farms more efficiently! We have simplified the collection of data and SharePoint farm settings. As part of this highly requested feature, we have removed the need to install or activate any software on your client's farm servers. To create snapshots, use the zero-footprint executable __SPDocKit Snapshot Wizard - Consultant__, or the new __[SPDocKit Powershell module](https://www.powershellgallery.com/packages/SysKit.SPDocKit.PS)__ if you prefer to use PowerShell. More information on how the new product works is available [here](#internal/how-to/create-snapshot).

The features above are designed to avoid leaving any trace of files in your client's environment.

Give it a try and let us know what you think! 

__Product version:__ 8.0.2 

__Build number:__ 10521 

__Release date:__ Oct 18, 2018 

[Click here to download the new release.](https://www.syskit.com/products/spdockit/download/)


## Features

* __PS Module__ and __SPDocKit Consultant Snapshot Wizard__ - As already mentioned above, these are the two ways of creating a snapshot. There is no need to install or activate any product in your client’s environment anymore. For more information on how to create a snapshot, see [this article.](#internal/how-to/create-snapshot)


* The __new XLSX export__ introduced to SPDocKit comes with built-in functionality to sort and filter data in each column! It is available on all reports, and compare results. The old export style is still available under a different name: Legacy Export as XLSX.

* __SharePoint 2019 is supported!__ SPDocKit has been tested on the latest SharePoint 2019 environments. All features are working flawlessly. Try it out yourself!

## Improvements

* __Improved category navigation!__ Category navigation is positioned on the left side of the main window and can be collapsed to create even more space for reports.

* __Each farm name is now automatically set__ based on the snapshot data, if available. Otherwise, the usual naming convention is used: Farm 1, Farm 2, etc. The # symbol is no longer a part of this naming, since it caused problems when used with cloud-based services.

* The __Enable Usage and Health Data Collection report has been renamed "Usage and Health Data Collection Enabled"__, and the status of __two additional timer jobs has been added__ (Microsoft SharePoint Foundation Usage Data Processing and Microsoft SharePoint Foundation Usage Data Import).

* The __TempDB Files__ Best Practice report now checks to see if the tempDB files are on a separate drive from Binaries, Data, and Log Files; however, it is possible for all the tempDB files to be on the same drive. For more information, consult the following [link](https://docs.syskit.com/bp/v1/databases/tempdb/files/). 

* The __Content Database Capacity__ Best Practice report now __shows a Data File Free Space column instead of Data File Full__.

* The __IIS Instance ID column has been added__ to the __IIS Sites report__.

* We have added the text "[MB]" to headers of Storage Maximum Level, Storage Warning Level, and Usage Storage columns on the __Site Collection Quotas report__, to clarify which measurement units are displayed.

* The __Snapshot filter can now be extended__, in which case it shows information about load depth, snapshot mode, and whether a snapshot is marked as a good configuration.

* The __latest snapshot is now automatically opened__ when viewing the Farm Explorer and Best Practices reports. The "Reopen last accessed snapshot on start up" option has been, therefore, removed from SPDocKit Options. 

* The __details of inner exceptions are now displayed__ if they occur while taking a snapshot to make the troubleshooting easier.

* __Multiple Export buttons have been replaced with one Export button__. The default export type is set to XLSX, with an available dropdown option where you can select a different export type. 

* Servers in the __Browse for Servers list__ in the Configuration Wizard are now listed in __alphabetical order__, so you can quickly find the server you need.


## Bug Fixes

* Fixed a bug where special characters in a report name could cause an error when exporting it to an Excel file. 

* Fixed a bug where the Source and Target rows of the Compare Results window were out of sync when the horizontal scroll was visible.

* Fixed a bug where a wrong total number of site collections was displayed on the Snapshot Wizard while taking a snapshot in the SharePoint 2016 environment.

* Fixed an issue where the Best Practice Wizard would result in a smart error when a DateTime type of column was selected on the Conditional Formatting step.

* Fixed a bug where changing between Farm Explorer and Best Practices reports caused the app to crash in multi-farm environments. 

* Fixed an issue where you could change steps on the Finish step of the Configuration Wizard, which resulted in an error. 

* Fixed a bug where AutoSPInstaller would cause a cast exception: "Unable to cast object of type 'System.DBNull' to type 'System.String'."

* Fixed an issue where the License Details form didn’t display the Name and Email values.

* Fixed a rare bug in various BP reports where filtering the underlying data for the report would cause a Syntax error exception.

* Fixed an issue where the Incremental Search BP report didn’t show an error, even when the setting was not in the defined range.  


## Discontinued Features

* __SPDocKit run mode__ has been replaced with new apps used with SPDocKit Consultant.
For more information, visit the [following link](#internal/how-to/create-snapshot).

* The __XML File__ option for saving snapshots has been removed.