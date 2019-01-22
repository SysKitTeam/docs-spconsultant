---
title: SPDocKit Consultant 8.0.3 — Release Note
description: >-
  This article describes improvements and bug fixes delivered in SPDocKit
  Consultant 8.0.3
author: Igor Mesarić
date: 16/11/2018
---

# SPDocKit Consultant 8.0.3

This is a service release containing minor improvements and bug fixes.

**Product version:** 8.0.3  
**Build number:** 10628  
**Release date:** Nov 16, 2018

[Click here to download the new release.](https://www.syskit.com/products/spdockit/download/)

## Improvements:

* Improved error handling when loading SP2019 IIS Settings Information. For more information read the following [article.](../faq/troubleshooting/troubleshooting/error-while-loading-iis-settings.md)
* Improved error handling when opening snapshots.

## Bug fixes:

* Resolved an issue involving the possibility that the PowerShell module could be run without elevated privileges, which resulted in snapshots with incomplete data loaded, causing further issues with reports. 
* Fixed a bug in which opening SPDocKit Consultant through double-clicking a SPDFarmx file resulted in a change of opened snapshot when navigating to Best Practice reports. 
* Resolved an issue involving the analysis of solutions not being performed when the load was performed with Snapshot Wizard - Consultant or PowerShell module.  
* Resolved an issue with the DB Server Hotfixes report, which wrongly displayed non-database servers in single server environments. 
* Fixed an issue in which Snapshot Wizard - Consultant would throw a smart error on load Cancel.
* Resolved an issue relating to the app throwing a smart error when trying to load an SP2007 snapshot.
* Fixed a bug involving the ESC key causing a smart error if pressed in specific situations in the Options dialog.
* Fixed a bug involving a smart error showing when saving passwords to a snapshot from the Passwords and Product Keys reports.
* Resolved an issue with the Project Server load in SharePoint 2016 and 2019 environments.

