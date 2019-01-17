---
title: >-
  Could not load Search Service Application, check your permissions or event
  log.
description: >-
  Article describes how to handle issue when Search Service Application load is
  not working properly.
author: Tomislav Sirovec
date: 18/6/2018
---

# Search Service Application Requirements

## Problem:

While trying to load a SharePoint farm I encountered the following error:

> _Could not load Search Service Application, check your permissions or event log._

and the event log displays the following error message:

> _The following service applications cannot be loaded:_  
> _Search Service Application – Cannot open database “Search\_Service\_Application\_DB\_dd13ba19a7bb4ffaafcc3e626e73c949” requested by the login. The login failed.  
> Login failed for user ‘CONTOSO\bob’._

## Solution:

The account running SPDocKit does not have the proper privileges to load the Search Service Application properties.

Here is what you need to do: 1. Open the **SharePoint Central Administration** of your farm. 2. Navigate to **Application Management &gt; Manage Service Applications**. 3. Select your app from the list of Service Applications and click **Permissions** on the ribbon. 4. Choose the account running SPDocKit from the popup dialog box and make sure it has **Full control** permission checked. 5. Repeat the process for the selected account but now in the **Administrators** group. Select your app from the list of Service Applications and click Administrators on the ribbon. 6. Choose the account running SPDocKit from the popup dialog box and make sure it has **Full control** permission checked. 7. Now when your account/user has the proper privileges, please restart the SPDocKit Snapshot Wizard. You should be able to load the Search Service Application properties now.

## Learn More

* [SharePoint On-Premises User Permissions Requirements](user-permission-requirements.md)

