---
title:  Error occurred while trying to load ‘Problems and Solutions’ and ‘Rule Definitions’
description: Article describes the issue of SPDocKit not being able to load Problems and Solutions and Rule Definitions.
author: Mia Tomaić
date: 18/5/2017
---

## Problem:
While trying to load the SharePoint farm the following errors occurred:
* Error occurred while loading Problems and Solutions.
* Error occurred while loading Rule Definitions.

There is an error message in the event log:
> *System.Data.SqlClient.SqlException: Cannot open database “SharePoint_AdminContent_bfe62573-2067-4090-a95a-39a13ba51086” requested by the login.  
The login failed.  
Login failed for user ‘CONTOSO\bob’*.

## Solution:
The user running the SPDocKit needs to have the [proper privileges](#internal/requirements/user-permissions-requirements) to retrieve information from the SharePoint farm. To fix this issue make sure the user has Shell access to the given content database, using the following PowerShell code to grant access:
```powershell
$spcdb = Get-SPContentDatabase SharePoint_AdminContent_bfe62573-2067-4090-a95a-39a13ba51086
Add-SPShellAdmin -UserName CONTOSO\Bob -Database $spcdb
```