---
title: Distributed Cache loading issue
description: >-
  Distributed Cache settings cannot be loaded because the server is not part of
  the Distributed Cache Cluster.
author: Iva Novoselic
date: 25/5/2017
---

# Distributed Cache loading issue

## **Summary**

SPDocKit Snapshot Wizard or SPDocKit PowerShell module do not load Distributed Cache settings data and display a warning message during the load:

{% hint style="warning" %}
**Please note!**  
Distributed Cache settings cannot be loaded on a server that is not part of a Distributed Cache Cluster.
{% endhint %}

This happens because SPDocKit Snapshot Wizard or SPDocKit PowerShell module query only the server it is installed on for Distributed Cache data, so if the server on which SPDocKit Consultant is running is not a host for the Distributed Cache service, no data will be loaded.

**Application version:** 4.1.0 and newer

## **Solution**

Take snapshot and run the load process from a server that is part of the Distributed Cache Cluster.

### **Workaround**

Distributed Cache API requires that the registry of the current server contains data providers and connection string for the cluster, or take snapshot on a server that is part of the Distributed Cache Cluster.

There is an unofficial workaround for this restriction which includes editing the registry of the server on which you are taking a snapshot, to include the fields required by the API. This means running a PowerShell script on the server in order to update the provider and connection string fields.

The registry fields will be correctly updated using this PowerShell script:

```bash
    if((Get-PSSnapin | Where {$_.Name -eq "Microsoft.SharePoint.PowerShell"})-eq $null)
    {Add-PSSnapin Microsoft.SharePoint.PowerShell;}

    $ConnectionString = (Get-SPDatabase | ?{$_.Type -eq "Configuration Database"}).DatabaseConnectionString
    Set-ItemProperty "HKLM:\Software\Microsoft\AppFabric\V1.0\Configuration" -Name ConnectionString -Value $ConnectionString
    Set-ItemProperty "HKLM:\Software\Microsoft\AppFabric\V1.0\Configuration" -Name Provider -Value "SPDistributedCacheClusterProvider"

    New-Item -Path "HKLM:\Software\Microsoft\AppFabric\V1.0\Providers\AppFabricCaching\SPDistributedCacheClusterProvider"
    New-ItemProperty -Path "HKLM:\Software\Microsoft\AppFabric\V1.0\Providers\AppFabricCaching\SPDistributedCacheClusterProvider" -Name "DisplayName" -Value "Microsoft SharePoint AppFabric Caching Service Configuration Store Provider" -PropertyType "string" -Force
    New-ItemProperty -Path "HKLM:\Software\Microsoft\AppFabric\V1.0\Providers\AppFabricCaching\SPDistributedCacheClusterProvider" -Name "Type" -Value "Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClusterCustomProvider, Microsoft.SharePoint, Version=15.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" -PropertyType "string" -Force
```

**Credit:** To learn more about this workaround, please visit the Wouter Bleeker blog.

**Status:** Not resolved.

