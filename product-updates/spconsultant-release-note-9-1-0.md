---
description: This article describes bug fixes delivered in SPDocKit Consultant 9.1.0.
---

# SPDocKit Consultant 9.1.0

**SPDocKit Consultant 9.1.0** is a minor release containing a couple of bug fixes.

**Product version:** 9.1.0  
**Build number:** 11074  
**Release date:** Mar 26, 2019  
  
[Click here to download the new release.](https://www.syskit.com/products/spdockit/download/)

## Bug Fixes

* Fixed a bug that occurred when resolving local group memberships when the group contained deleted users from trusted forests. The bug would cause the local groups to appear empty.  The following error was thrown:  `Error while resolving memberships for group <groupName> on the <serverName> server. System.DirectoryServices.AccountManagement.PrincipalOperationException: An error (1332) occurred while enumerating the group membership. The member’s SID could not be resolved.`
* Fixed a bug where the Health Analyzer Problems report erroneously displayed the date and time value in the Last Modified column. Instead of the actual value, ‘1/1/0001 12:00:00 AM’ was displayed as the date and time.



