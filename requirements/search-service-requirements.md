---
title: Could not load Search Service Application, check your permissions or event log.
description: Article describes how to handle issue when Search Service Application load is not working properly.
author: Tomislav Sirovec
date: 18/6/2018
---
### Problem:
While trying to load a SharePoint farm I encountered the following error:
> *Could not load Search Service Application, check your permissions or event log.*

and the event log displays the following error message:

> *The following service applications cannot be loaded:*  
*Search Service Application – Cannot open database “Search_Service_Application_DB_dd13ba19a7bb4ffaafcc3e626e73c949” requested by the login. The login failed.  
Login failed for user ‘CONTOSO\bob’.*

### Solution:
The account running SPDocKit does not have the proper privileges to load the Search Service Application properties.

Here is what you need to do:
1. Open the **SharePoint Central Administration** of your farm.
2. Navigate to **Application Management > Manage Service Applications**.
3. Select your app from the list of Service Applications and click **Permissions** on the ribbon.
4. Choose the account running SPDocKit from the popup dialog box and make sure it has **Full control** permission checked.
5. Repeat the process for the selected account but now in the **Administrators** group. Select your app from the list of Service Applications and click Administrators on the ribbon.
6. Choose the account running SPDocKit from the popup dialog box and make sure it has **Full control** permission checked.
7. Now when your account/user has the proper privileges, please restart the SPDocKit Snapshot Wizard. You should be able to load the Search Service Application properties now.

### Learn More
* [SharePoint On-Premises User Permissions Requirements](#internal/requirements/user-permissions-requirements)
