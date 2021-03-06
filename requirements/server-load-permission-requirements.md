---
description: This article lists all permissions necessary for SPDocKit Snapshot Wizard or SPDocKit PowerShell module to gather information about SharePoint farm servers.
---

# Server Load Permission Requirements

## SharePoint Server Information

During the Snapshot creation process, SPDocKit Snapshot Wizard or SPDocKit PowerShell module will try to retrieve information about your servers.

{% hint style="warning" %}
**Please note!**  
The following permissions on your servers are optional, but depending on them, some or all information about your server configuration and the corresponding best practices reports will not be available to SPDocKit Snapshot Wizard or SPDocKit PowerShell module when creating a snapshot.
{% endhint %}

### Required permissions

In order to allow SPDocKit Snapshot Wizard or SPDocKit PowerShell module to successfully gather all the information about your SharePoint farm servers, the following permissions are necessary:

* **Local Administrator** on the server
* **Windows Update service** up and running

### Granting permissions

To add the user running SPDocKit Snapshot Wizard or SPDocKit PowerShell module to the **Local Administrator group** follow these steps:

1. On the server, open the **Local Users and Groups** management console. Find it by typing **"Edit local users and groups"** or **"lusrmgr.msc"** in Windows Search.
2. Under Groups, find the **Administrators** group.
3. Click the **Add** button and enter the user accounts running SPDocKit Consultant.
4. Confirm your changes by clicking **OK**.

In case you have a very strict security policy and cannot add this account to the **Local Administrators** group, you can use the following procedure to get most of the reports working:

* Add your SPDocKit Snapshot Wizard or SPDocKit PowerShell module account to the following local groups: **Backup Operators** and **Performance Log Users**. This will allow us to remotely execute WMI queries and get information about SQL servers.
* Start **winmgmt.msc**, right click WMI Control and select Properties.
* Go to the **Security** tab and expand the Root node. In the expanded list select **cimv2** and click on the **Security** button.
* Click on **Advanced** button, then click **Add…** and enter the desired user and click OK.
* Select option **This namespace and subnamespaces** in a dropdown list Apply to.
* Make sure that you select **Enable Account** and **Remote Enable** on the **Allow list** and then click OK four times.

To start the **Windows Update service**, open the Service Microsoft Management Console, right-click the service and choose **Start**.

## SQL Server Information

There are some additional permission requirements necessary to load SQL servers information.

{% hint style="warning" %}
**Please note!**  
The following permissions on your SQL servers are optional, but depending on them, some or all information about your SQL server configuration and the corresponding Best Practices reports will not be available to SPDocKit Snapshot Wizard or SPDocKit PowerShell module when creating a snapshot.
{% endhint %}

### Required permissions

In order to allow SPDocKit Snapshot Wizard or SPDocKit PowerShell module to gather all the information about your SQL servers successfully, the following permissions are necessary:

* **Sysadmin** server role

In case that you can’t give those permissions due to security requirements, you can use the following permissions to get most of the SQL specific reports working:

* **Public** server role
* **Dbcreator** server role and **VIEW SERVER STATE** permission
* **Dbaccess** permission on **model** database
* **Db\_owner** database role on each of the affected databases

### Granting permissions

Follow these steps to grant the required permissions:

1. Create a new user on the SQL server that will be used by SPDocKit Snapshot Wizard or SPDocKit PowerShell module.
2. Add the **sysadmin** role to your SPDocKit Snapshot Wizard or SPDocKit PowerShell module account.

In case you have a very strict security policy and cannot add the sysadmin role to the SPDocKit Snapshot Wizard or SPDocKit PowerShell module account, you can use the following procedure to get most of the SQL reports working:

1. Create a new user on the SQL server that will be used by SPDocKit Snapshot Wizard or SPDocKit PowerShell module.
2. Add the **dbcreator** role to your SPDocKit Snapshot Wizard or SPDocKit PowerShell module account and execute the following T-SQL query:

   ```sql
      USE master  
      GO  
      GRANT VIEW SERVER STATE TO “DOMAIN\ACCOUNT”
   ```

3. Execute following T-SQL query to add necessary permissions:

   ```sql
      USE model  
      GO  
      EXECUTE sp_grantdbaccess 'DOMAIN\ACCOUNT'
   ```

To grant the **db\_owner** database role to the SPDocKit Snapshot Wizard or SPDocKit PowerShell module accounts, follow these steps:

1. Connect to your SQL server using **SQL Server Management Studio**.
2. Navigate to **Security** &gt; **Logins** and select the SPDocKit Snapshot Wizard or SPDocKit PowerShell module account.
3. Right-click the account and open the **Login Properties** dialog.
4. Under **User Mappings**, ensure that the account has the **db\_owner** database role for all affected databases.

## Project Server Information

During the snapshot creation process, SPDocKit Snapshot Wizard or SPDocKit PowerShell module will try to retrieve information about your Project server sites.

{% hint style="warning" %}
**Please note!**  
The following permissions on your Project server sites are optional, but depending on them, some or all information about your Project server sites configuration reports will not be available to SPDocKit Snapshot Wizard or SPDocKit PowerShell module when creating a snapshot.
{% endhint %}

### Required Permissions

In order to allow SPDocKit Snapshot Wizard or SPDocKit PowerShell module to successfully gather all the information about your Project server sites the following permissions are necessary:

* **Account running SPDocKit Snapshot Wizard or SPDocKit PowerShell module** needs to be a member of the Project Server **Administrators** group on each of the Project server sites

### Granting permissions

To add your SPDocKit Snapshot Wizard or SPDocKit PowerShell module account to the Administrators group, follow these steps:

1. In a browser, navigate to your Project server site.
2. Click **Settings** &gt; **PWA Settings** to open up the PWA Settings page.
3. Under **Security** click **Manage Users**.
4. Click **New User** and add your **SPDocKit Snapshot Wizard or SPDocKit PowerShell module user account**.
   * Under **User logon account** specify the **Domain\Username** of the **SPDocKit Snapshot Wizard or SPDocKit PowerShell module user account**.
   * Under **Security Groups** ensure that this user is a member of the **Administrators** security group.

