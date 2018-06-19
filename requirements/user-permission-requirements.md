---  
title: SharePoint On-Premises User Permissions Requirements
author: Tomislav Sirovec
date: 17/6/2018
description: This article lists required privileges to load SharePoint settings with tutorial how to acquire those privileges.
--- 
To run SPDocKit and to retrieve all SharePoint settings you want to document, both the user running SPDocKit and the SPDocKit service account need to have proper privileges. Here is the list of required privileges to load SharePoint farm settings:

1. __Local Administrators__ and __WSS_ADMIN_WPG group member__ on every machine in the SharePoint farm. Required to retrieve list of installed applications on farm servers.
2. __SharePoint farm administrator__. Required to retrieve SharePoint farm settings.
3. __Member of SharePoint_Shell_Access role__ on SharePoint Server databases. Required to retrieve particular SharePoint farm properties via PowerShell.
4. Special privileges for the __Service Account__: Service account needs to have privileges listed above as well as the __Log on as a Service__ right. [Click here for instructions](https://goo.gl/MRGS73) on how to configure that right.
5. [Server specific requirements](#internal/requirements/server-load-permission-requirements/) needed to retrieve additional server configuration data (RAM, processors, disk space…) and SQL Server configuration information for DB servers.
6. [Search service application requirements](#internal/requirements/search-service-requirements/) needed to retrieve Search service application configuration data (content sources, crawl rules, managed properties, search topologies...).
7. [User Profile service application requirements](#internal/requirements/user-profile-service-requirements/) needed to retrieve User Profile service application configuration data (Synchronization Connections, MySite Settings, Audiences, User Profile Properties...).

Here is how you can give user these privileges:

#### To add a user account to the __Local Administrators__ group (repeat the same steps for __WSS_ADMIN_WPG__):
  * On the server, click Start, right-click Computer, and then click __Manage__.
  * Navigate to Configuration, expand __Local Users and Group__ and then click Groups.
  * Right-click the Administrators group, and then click __Add to Group__.
  * In the Administrators Properties dialog box, click __Add__.
  * In the Select User, Computers, or Groups dialog box, in the Enter the object names to select box, type the account name on which you want your worker process to run (for example, __Domain\YourAccount__), and then click OK.
  * In the Administrators dialog box, click OK.
  * Close the Server Manager screen.

#### To add a user account to __SharePoint farm Administrators__ group:
  * Open SharePoint __Central Administration__.
  * Navigate to Security > Manage the farm administrators group.
  * Use the __New__ button to add users to this group.

#### To add a user account to __SharePoint_Shell_Access role__:
  * Open SharePoint Management Shell.
  * Type the following PowerShell command: `<Add-SPShellAdmin -UserName DOMAIN\YourAccount>` [(click here to learn more)](http://technet.microsoft.com/en-us/library/ff607596.aspx).
  * If you want to grant PowerShell shell access to a single database [check this article](http://technet.microsoft.com/en-us/library/ff607596.aspx) for more details.
  * If you want to grant PowerShell shell access to all content databases, run this script [download Configure-SPShellAdmin.ps1](#internal/_assets/Configure-SPShellAdmin.zip):

    ```powershell
    if((Get-PSSnapin | Where {$_.Name -eq "Microsoft.SharePoint.PowerShell"})-eq $null) 
    {Add-PSSnapin Microsoft.SharePoint.PowerShell;}  
    cls  
    $username = Read-Host "Enter username";  
    Get-SPDatabase | ForEach-Object {Add-SPShellAdmin -UserName $username -database $_.Id}
    ``` 

 
  Please note:
  * The cmdlet Add-SPShellAdmin is going to apply to all current SharePoint databases. If more SharePoint databases are added in the future, you might have to re-run the cmdlet again.
  * The cmdlet might fail in some environments; please contact us for further assistance.
     
### SPDocKit database requirements

#### Creating a new database

To be able to create a new SPDocKit dedicated database, the user account running the installation and configuration wizard (i.e. install account) should be granted both the __dbcreator__ and __securityadmin__ roles on the preferred SQL Server. This allows the account to create a new database and to assign proper privileges after creation. The install account will be automatically given __db_owner__ privileges on the newly created database, if possible. Otherwise, it is advised that the account is given that privilege manually, as it is needed for upgrading the database.

#### Privileges required to run the application

These privileges will be granted automatically when a new SPDocKit database is created or during a database upgrade.

* SPDocKit service account will be granted the __SPDocKit_service_role__ role on the SPDocKit database. This role will make the service account a member of the __db_datawrite__ and __db_datareader__ roles and grant __EXECUTE__ permissions on all the stored procedures in the database.
  * In the event that the SPDocKit install account is not in the __securityAdmin__ role, please add the SPDocKit service account manually to the __SPDocKit_service_role__. [Consult the following article](#internal/faq/troubleshooting/error-adding-service-account-to-role/) for additional information.
 * The account running load from the SPDocKit console needs to have the same privileges as the SPDocKit service account (see above).

### Workstation Requirements

When running the application on a workstation, the SPDocKit user connecting to any SharePoint 2010, SharePoint 2013 or SharePoint 2016 site will need to be granted __Site Collection Administrator__ privileges for each site he is trying to explore and manage.

To connect to an existing SPDocKit database from the workstation, the SPDocKit user will need to be granted the __db_datareader__ rights on SPDocKit database.

### Error Message

If the user does not have proper privileges, the following error message will be shown:
> “You do not have privileges to load the current farm! Please contact your administrator.”
