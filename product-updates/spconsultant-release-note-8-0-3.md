---
title: SPDocKit Consultant 8.0.3 — Release Note
description: This article describes improvements and bug fixes delivered in SPDocKit Consultant 8.0.3
author: Igor Mesarić
date: 16/11/2018
---

This is a service release containing minor improvements and bug fixes. 

__Product version:__ 8.0.3  
__Build number:__   10628     
__Release date:__ Nov 16, 2018    

[Click here to download the new release.](https://www.syskit.com/products/spdockit/download/)

## Improvements:
* Improved error handling when loading SP2019 IIS Settings Information. For more information read the following [article.](#internal/faq/troubleshooting/error-while-loading-iis-settings)
* Improved error handling when opening snapshots.
* Improved error logging in the Event log. 

## Bug fixes:
* Resolved an issue where the PowerShell module could be run without elevated privileges, which resulted in snapshots with incomplete data loaded which caused further issues with reports. 
* Fixed a bug where opening SPDocKit Consultant through double-clickig a SPDFarmx file resulted in a change of opened snapshot when navigating to Best Practice reports. 
* Resolved an issue where the analysis of solutions was not performed when the load was performed with Snapshot Wizard - Consultant or PowerShell module.  
* Resolved an issue with the DB Server Hotfixes report which wrongly displayed non-database servers in single server environments. 
* Fixed an issue where Snapshot Wizard - Consultant would throw a smart error on load Cancel.
* Resolved an issue where the app would throw a smart error when trying to load an SP2007 snapshot.
* Fixed a bug where the ESC key would cause a smart error if pressed in specific situations in the Options dialog.
* Fixed a bug where a smart error would show when saving passwords to a snapshot from the Passwords and Product Keys reports.
* Resolved an issue with the project server load on SP2019 environments.