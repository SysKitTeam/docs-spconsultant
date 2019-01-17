---
title: Security
description: SPDocKit security related questions
author: Iva Novoselic
date: 22/5/2017
---

# security

## Does SPDocKit make changes to the farm?

SPDocKit uses only Microsoft provided and supported SharePoint APIs and PowerShell to retrieve information about the structure of a SharePoint farm. During load operations nothing is being changed in the farm structure.

Our load process does not require access to SharePoint databases with the exception of the SharePoint logging database that we use to gather feature usage. Access to this database is an approach supported by Microsoft to retrieve information about usage. SharePoint administrators using SPDocKit can choose not to connect to this database during load operations.

## Can a saved farm configuration be viewed by everyone?

As long as the folder where snapshots are stored is protected, no one will be able to open these files. The files are not encrypted. This is handled by Windows NTFS permissions.

## If the Central Administration and the websites are running in SSL, will SPDocKit also use SSL?

We use APIs, not HTTPS, to retrieve information. The product can only run on a SharePoint server, so there is no server-to-server communication that can be intercepted.

## Owing to security restrictions, clients aren't able to grant access to SharePoint production farms — is there a workaround?

SysKit has helped some of the largest organizations worldwide to work around this issue by installing SPDocKit on a testing or non-production server. This is the best solution if you are unable to access the SP production server/farm.

## How does SPDocKit store passwords? Is storing passwords optional or mandatory?

SPDocKit can store your passwords and products keys in the farm documentation files. If you decide to enter these, you will be prompted to provide an additional password \(master password\) that will be used to encrypt these files with AES 256bit encryption. You will only be able to retrieve these passwords if you provide the master password again.

