---
title: Error while loading IIS Settings Information
description: This article explains how to handle the issue with IIS Settings load on SharePoint 2019.
author: Igor Mesarić    
date: 07/11/2018
---

## Problem:
While trying to load a SharePoint 2019 farm with the enabled IIS Settings Information option, the following error message appears:

> *IIS 6 Management Metabase Compatibility required.*

The following error message is stored in the event log:

> *Error while loading SP2019-SRV*

> *Acceleratio.SPCommon.SharePointCrawler.IISCompatibilityMissingException: IIS 6 Management Metabase Compatibility required.*
  *at Acceleratio.SPDocKit.Administration.IISSettingsLoader.IISMetabaseReader.GetAppPools(String serverAddress, ConfigReader configReader)*
  *at Acceleratio.SPDocKit.Administration.IISSettingsLoader.IISLoaders.IIS7Loader.Load()*
  *at Acceleratio.SPDocKit.Administration.ServerDetailsLoader.#ca3.#uZgb()*
  *at Acceleratio.SPCommon.TimeoutableAction.#392.#5Ygb()*

## Solution:
To successfully load IIS Settings, the IIS 6 Metabase Compatibility role has to be enabled. 

__Please note:__ A server restart could be required for the changes to take effect.

To enable the role, follow these steps:

1. Open the Server Manager on IIS server
1. a) On the Dashboard screen, select the __Add roles and features__ option<br/>
__OR__<br/>
b) On the left side menu, click the __Local Server__ option, navigate to the __Roles and Features__ section, and select __Add Roles and Features__ option in the __Tasks__ drop-down menu on the right side of the screen. The __Add Roles and Features Wizard__ opens.
1. __Before You Begin__ step - continue to the next step by clicking Next.
1. __Installation Type__ step - make sure the __Role-base or feature-based installation__ option is selected.
1. __Server Selection__ step - make sure the IIS server is selected.
1. __Server Roles__ step - make sure the __IIS 6 Metabase Compatibility__ option is checked. You can find it under Web Server (IIS) > Management Tools > IIS 6 Management Compatibility > IIS 6 Metabase Compatibility.
![Add Roles and Features Wizard](images/faq/add_roles_and_features_wizard.png)
1. __Features__ step - continue to the next step.
1. __Confirmation__ step - check the __Restart the destination server automatically if required__ option and click __Install__.
1. __Results__ step - displays the installation progress. Once the installation is finished, the __Installation succeeded__ message is displayed. 

__Please note:__ Make sure to install the role on all Web Front End servers in a Farm in order to collect the IIS Settings Information.

SPDocKit Snapshot Wizard - Consultant and SPDocKit PowerShell module will now be able to collect the server's IIS Settings Information.