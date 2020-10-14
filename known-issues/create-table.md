---
title: CREATE TABLE permissions denied
description: >-
  An error appears in the ULS log, stating that SPDocKit Snapshot Wizard or
  SPDocKit PowerShell module processes are trying to create tables in SharePoint
  databases.
author: Matija Hanzic
date: 28/6/2018
---

# CREATE TABLE permissions denied

## **Summary**

Errors appear in the ULS log that states that SPDocKit Snapshot Wizard or SPDocKit PowerShell module processes are trying to create tables in SharePoint databases.

First and foremost, SPDocKit Snapshot Wizard or SPDocKit PowerShell module does not create tables or modify SharePoint databases during the snapshot process. The problem occurs when there is a permissions issue when taking a snapshot.

SPDocKit Snapshot Wizard and SPDocKit PowerShell module query the NeedsUpgrade property of the SharePoint database. The query fails because of the lack of **SELECT** permission from the Versions table. This causes SharePoint to erroneously conclude that the database should be upgraded, but fails because the **CREATE TABLE** permission is missing as well. When the permissions are correctly set up, there are no attempts to create tables.

The issue can easily be reproduced in PowerShell by running the snapshot is taken using the account that lacks sufficient permissions:

```bash
    $myDB = Get-SPDatabase | ?{$_.Name -eq "[SPDatabaseName]"}
    $myDB.NeedsUpgrade
```

After running these commands, two things can be noticed:

1. The NeedsUpgrade property will return the wrong value: it will always be true. 
2. CREATE TABLE errors will appear in the ULS log.

## **Solution**

Please ensure that the user account running the SPDocKit Snapshot Wizard or SPDocKit PowerShell module has the required permissions on the database in question. You need to manually add the **SELECT** permission to the Versions table on all of the affected SharePoint databases.

1. Run the following SQL query to grant the necessary permissions:

   ```sql
      USE [SPDatabaseName];  
      GRANT SELECT ON OBJECT::[dbo].[Versions] TO [DOMAIN\USERNAME];  
      GO
   ```

2. Now, when your account/user has the proper privileges, please restart/rerun the Snapshot Wizard or the PowerShell Module.

