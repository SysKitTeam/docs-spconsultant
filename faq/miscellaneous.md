---
title: Troubleshooting
description: SPDocKit troubleshooting questions
author: Mia Tomaić
date: 22/5/2017
---


## How can I update the product versions offline?
[Here](https://my.syskit.com/Utilities/productversions.aspx) is the link for the offline update. 

Click the **Generate button**. Download **all of** the files, copy them to the server that has no internet access and overwrite the existing files (default location: **%ProgramData%\SPDocKit\Settings**).

After you copy these files, please restart the application in order to apply the changes.

## I am getting "The service did not respond to the start or control request in a timely fashion".

This is the issue on servers that don’t have access to the Internet. The Windows server will try to check the code signing certificate that was used to sign the application executables. Allow Internet access on the server, then start the service and the issue is solved. Please note that you need to do this only once — the first time Windows will check the SysKit code signing certificate and from then on it will work fine.

If this is not possible [contact us](https://www.syskit.com/company/contact-us/) and we will provide you with a certificate and instructions on how to import it to your problematic server.

## I am getting "This product cannot be activated since it is not a SharePoint Server or you do not have the right privileges to access the SharePoint Farm. Check if SharePoint is installed or contact your administrator".

### Problem:

When I tried to load a SharePoint farm with SPDocKit I received the following error:

>*This product cannot be activated because this is not a SharePoint Server or you do not have the right privileges to access the SharePoint Farm. Check if SharePoint is installed or contact your administrator.*

### Solution:
* The product needs to run on the same server as SharePoint, so make sure SharePoint is installed on the server where you are trying to load the farm.
* In order to load the SharePoint farm you need to have proper privileges. Check [this article](#internal/requirements/user-permissions-requirements) for more details.


## Error occurred while upgrading to the latest version.

### Problem:
You might encounter the following error if you are upgrading to the latest version of the application:

>*Error 1001. An exception occurred while uninstalling. The exception will be ignored and the uninstall will continue. However the application might not be fully uninstalled after the uninstall is complete. -> The specified service does not exists as an installed service.*

When this error occurs you are not able to start the application and you cannot Remove/Repair it from Control Panel > Programs.

### Solution:
The installation was not able to remove the Windows service. The existing installation needs to be repaired and then removed before you can proceed with the upgrade.

Here is what you need to do:
1. Obtain the original MSI file you used to install the product (product version e.g. 1.0.3 is listed in **Control Panel > Programs**, but you can [contact us](https://www.syskit.com/company/contact-us/) to obtain the original installation).
2. Right-click the MSI file and choose **Repair** to repair the application.
3. Use **Control Panel > Programs** to uninstall the application.
4. Once uninstalled, you can **install** the latest version as planned.

During this procedure you might get the “Service Marked for Deletion” error message. In that case, make sure the Services dialog box is not running **(Control Panel > Administrative Tools > Services)**. If the dialog box is not running you will have to restart your computer before proceeding to the next step.


## Should this program only be opened on the server console or is it okay to open it via Remote Desktop?

The application will work on both the console and the Remote Desktop session.

## I am having problems running the application when UAC (User Access Control) is enabled.

1. Locate the application installation directory in Program files and find the SPDocKit.exe file (usually: C:\Program files\SysKit\SPDocKit).
2. Create a shortcut for that file on the desktop.
3. To execute the application, right-click the shortcut then choose Run as the administrator.
4. The UAC dialog box will be shown and you will be prompted to run the application as the administrator.
5. Click Yes and SPDocKit will run without any issues.

**Please note:** *You must create a shortcut that points directly to the file in the application directory, and not to the file in the Start menu.*

## Cannot upgrade as "The specified service already exists".

### Problem:
When trying to upgrade to the latest version of SPDocKit you might receive an error:

>*The specified service already exists.*

### Solution:
The previous version has not been removed correctly. Here is what you need to do:

1. Go to **Add/Remove programs** and uninstall the SPDocKit Consultant manually (if the product is not listed, you do not have the proper privileges or somebody else installed the application, e.g. an Administrator user, so logon as the user who initially installed the application then remove it).
2. Once the program has been removed you can restart the new installation you have downloaded and install the application.

### Additional notes:
In case you encounter a similar error again, try the following:

Stop the SPDocKit Service in the services MMC console, then open the Command Prompt and type in the following to delete the service:

>*sc delete SPDocKitService*

The service will be reinstalled with the new installation.

## SQL server and SharePoint product versions warning
We have an internal list of SQL Server and SharePoint product versions so that we can match build numbers to description. For example, if your SQL server build number is 10.50.1765.0, you will see “SQL Server 2008 R2 CU6, 21 Feb 2011” in your reports.  
If the warning appears as in SPDocKit, you can click the Update button and SPDocKit will fetch the internal list from our servers, if you have Internet access on your servers.

## I am receiving a 2103 error code during installation. How do I fix it?
In order to install SPDocKit on a Windows server you will have to run it with administrative privileges.

## Network ports required for gathering the data.

If you have a firewall between the server hosting the application and the servers that are being monitored you need to have the following ports open (In brackets are the rule names in Windows Server 2008):

* All ports from 49152 and above should be open – during the IIS load we use Microsoft component that utilize dynamic ports and that is the main reason why we require to open these ports on firewall. [Read more](https://support.microsoft.com/en-us/help/929851/the-default-dynamic-port-range-for-tcp-ip-has-changed-in-windows-vista)
* Inbound rules on Windows Server 2008, 2008 R2, 2012 and 2012 R2 are (this is inside the windows firewall):
  * COM+ Network Access (DCOM-IN)
  * COM+ Remote Administration (DCOM-In)
  * File and printer sharing (NB-Session-In)
  * Network Discovery (NB-Name-In)
  * Network Discovery (NB-Datagram-In)

* In case you have the third party firewall the ports are:
    * RPC TCP 135
    * NetBIOS Datagram Service UDP 138   
    * NetBIOS Name Resolution UDP 137
    * NetBIOS Session Service TCP 139

## What should I do to stop receiving ''There is no data to show for this object'' for all User Profile Reports?

This message is sometimes generated when there are insufficient rights given to an end user. To load User Profile Synchronization connections you need to do the following:

### Solution:

1. Start the __User Profile Synchronization Service__.
1. The account used to create a snapshot needs to be a member of the __Administrators__ group of the User Profile Service Application and have __Full Control__ access. This is done by adding them to the User Profile Service Administrators group using the “Administrators” button in SharePoint __Central Administration > Application Management > Manage Service Applications__.
All accounts taking a snapshot must have the same level of access.


For more information, please see the [following article](#internal/requirements/user-profile-service-requirements).