# SharePoint On-Premises User Permissions Requirements

To run SPDocKit Consultant and to retrieve all SharePoint settings you want to document, the user running SPDocKit Consultant needs to have proper privileges. Here is the list of required privileges to load SharePoint farm settings:

1. **Local Administrators** and **WSS\_ADMIN\_WPG group member** on every machine in the SharePoint farm. Required to retrieve list of installed applications on farm servers.
2. **SharePoint farm administrator**. Required to retrieve SharePoint farm settings.
3. **Member of SharePoint\_Shell\_Access role** on SharePoint Server databases. Required to retrieve particular SharePoint farm properties via PowerShell.
4. [Server specific requirements](server-load-permission-requirements.md) needed to retrieve additional server configuration data \(RAM, processors, disk space…\) and SQL Server configuration information for DB servers.
5. [Search service application requirements](service-application-permission-requirements.md#search-service-application-requirements) needed to retrieve Search service application configuration data \(content sources, crawl rules, managed properties, search topologies...\).
6. [User Profile service application requirements](service-application-permission-requirements.md#user-profile-service-application-requirements) needed to retrieve User Profile service application configuration data \(Synchronization Connections, MySite Settings, Audiences, User Profile Properties...\).

Here is how you can give user these privileges:

## To add a user account to the **Local Administrators** group \(repeat the same steps for **WSS\_ADMIN\_WPG**\):

* On the server, click Start, right-click Computer, and then click **Manage**.
* Navigate to Configuration, expand **Local Users and Group** and then click Groups.
* Right-click the Administrators group, and then click **Add to Group**.
* In the Administrators Properties dialog box, click **Add**.
* In the Select User, Computers, or Groups dialog box, in the Enter the object names to select box, type the account name on which you want your worker process to run \(for example, **Domain\YourAccount**\), and then click OK.
* In the Administrators dialog box, click OK.
* Close the Server Manager screen.

## To add a user account to **SharePoint farm Administrators** group:

* Open SharePoint **Central Administration**.
* Navigate to Security &gt; Manage the farm administrators group.
* Use the **New** button to add users to this group.

## To add a user account to **SharePoint\_Shell\_Access role**:

* Open SharePoint Management Shell.
* Type the following PowerShell command:  `<Add-SPShellAdmin -UserName DOMAIN\YourAccount>` [\(click here to learn more\)](http://technet.microsoft.com/en-us/library/ff607596.aspx)
* If you want to grant PowerShell shell access to a single database [check this article](http://technet.microsoft.com/en-us/library/ff607596.aspx) for more details.
* If you want to grant PowerShell shell access to all content databases,  download: Configure-SPShellAdmin.ps1

{% file src="../.gitbook/assets/configure-spshelladmin.zip" %}

```bash
if((Get-PSSnapin | Where {$_.Name -eq "Microsoft.SharePoint.PowerShell"})-eq $null) 
{Add-PSSnapin Microsoft.SharePoint.PowerShell;}  
cls  
$username = Read-Host "Enter username";  
Get-SPDatabase | ForEach-Object {Add-SPShellAdmin -UserName $username -database $_.Id}
```

{% hint style="warning" %}
**Please note!**  
The cmdlet **Add-SPShellAdmin** is going to apply to all current SharePoint databases. If more SharePoint databases are added in the future, you might have to re-run the cmdlet again.

The cmdlet might fail in some environments; please [contact us](https://www.syskit.com/company/contact-us/) for further assistance.
{% endhint %}

