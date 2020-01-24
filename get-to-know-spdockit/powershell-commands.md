---
title: PowerShell available commands
description: This article describes the available PowerShell commands
author: Tomislav Sirovec
date: 24/8/2018
---

# PowerShell Commands

As explained in the [create snapshot article](../how-to/create-snapshot.md) there are two ways of creating a snapshot on your clients farm. Using either the SPDocKit Snapshot Wizard or the SPDocKit PowerShell Module.

If you decided to use a PowerShell Module, here is a list of all the available commands. You can also view them in the PowerShell console it self, by running:

```bash
Get-Help New-SPDocKitSnapshot -full
```

General information on how to create a snapshot can be viewed \[here\]../how-to/create-snapshot.md\).

If you need further assistance, please [contact us](https://www.syskit.com/company/contact-us/).

### Syntax

```bash
    New-SPDocKitSnapshot [-SiteCollectionsOff] [-PersonalSitesOff][-FeaturesAndSolutionsOff] [-DatabasePermissionsOff] [-ProgramsAndUpdatesOff] [-SQLServerConfigurationOff] [-IISSettingsOff] [-ProjectServerSettingsOff] [-ProjectServerProjectsOff] [-Location [<String>]] [-NumberOfThreads [<UInt16>]] [-ServerLoadGlobalTimeout [<UInt16>]] [-ServerLoadOperationTimeout [<UInt16>]] [-FarmAccessTimeout [<UInt16>]] [<CommonParameters>]
```

### Description

Crawls the SharePoint farm, creating a snapshot file containing the current state of the farm's configuration at the specified location. The created file can then be used by SPDocKit Consultant to browse the configuration and document it. Note that this process might take a while, depending on the farm size and the settings selected.

By default, the New-SPDocKitSnapshot cmdlet does a full load of a SharePoint farm and creates the snapshot file in the current working directory. You can exclude the load of some settings by specifying the corresponding parameter.

Errors that occur will be logged in the Windows Event Log with the source SPDocKit PS.

Parameters:

```bash
-SiteCollectionsOff  or  -noSites
    If set, site collections will not be loaded. Load depth will be set to web applications.

    Required?                    false
    Position?                    named
    Default value                
    Accept pipeline input?       
    Accept wildcard characters?  

-PersonalSitesOff  or  -noPers
    If set, personal sites will be skipped.

    Required?                    false
    Position?                    named
    Default value                
    Accept pipeline input?       
    Accept wildcard characters?  

-FeaturesAndSolutionsOff  or  -noFeats
    If set, features and solutions will not be loaded.

    Required?                    false
    Position?                    named
    Default value                
    Accept pipeline input?       
    Accept wildcard characters?  

-DatabasePermissionsOff  or  -noDbPerm
    If set, database permissions will not be loaded.

    Required?                    false
    Position?                    named
    Default value                
    Accept pipeline input?       
    Accept wildcard characters?  

-ProgramsAndUpdatesOff  or  -noUpdates
    If set, programs and updates will not be loaded.

    Required?                    false
    Position?                    named
    Default value                
    Accept pipeline input?       
    Accept wildcard characters?  

-SQLServerConfigurationOff  or  -noSQL
    If set, SQL Server configuration will not be loaded.

    Required?                    false
    Position?                    named
    Default value                
    Accept pipeline input?       
    Accept wildcard characters?  

-IISSettingsOff  or  -noIIS
    If set, IIS settings will not be loaded.

    Required?                    false
    Position?                    named
    Default value                
    Accept pipeline input?       
    Accept wildcard characters?  

-ProjectServerSettingsOff  or  -noPSSettings
    If set, Project Server settings and Project Server projects will not be loaded.

    Required?                    false
    Position?                    named
    Default value                
    Accept pipeline input?       
    Accept wildcard characters?  

-ProjectServerProjectsOff  or  -noPSProj
    If set, Project Server projects will not be loaded.

    Required?                    false
    Position?                    named
    Default value                
    Accept pipeline input?       
    Accept wildcard characters?  

-Location  or  -l <String>
    Defines the location on the disk where the SPDocKit snapshot file will be saved.

    Required?                    false
    Position?                    named
    Default value                Current working directory
    Accept pipeline input?       
    Accept wildcard characters?  

-NumberOfThreads  or  -threads <UInt16>
    Defines the number of threads that will be used for parallel load. Maximum number is 32.

    Required?                    false
    Position?                    named
    Default value                4
    Accept pipeline input?       
    Accept wildcard characters?  

-ServerLoadGlobalTimeout  or  -globalTimeout <UInt16>
    Defines the timeout for the entire server load process in seconds.

    Required?                    false
    Position?                    named
    Default value                1800
    Accept pipeline input?       
    Accept wildcard characters?  

-ServerLoadOperationTimeout  or  -operationTimeout <UInt16>
    Defines the timeout for a single server load in seconds.

    Required?                    false
    Position?                    named
    Default value                900
    Accept pipeline input?       
    Accept wildcard characters?  

-FarmAccessTimeout  or  -accessTimeout <UInt16>
    Defines the timeout for accessing the SharePoint farm in seconds.

    Required?                    false
    Position?                    named
    Default value                120
    Accept pipeline input?       
    Accept wildcard characters?  

-Verbose
    If set, a log file will be created and saved to the same directory as the snapshot file.

    Required?                    false
    Position?                    named
    Default value                
    Accept pipeline input?       
    Accept wildcard characters?  

<CommonParameters>
    This cmdlet supports the common parameters: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, WarningVariable, OutBuffer, PipelineVariable, and OutVariable. For more information, see about_CommonParameters [here](http://go.microsoft.com/fwlink/?LinkID=113216).
```

Outputs:

```bash
———————— EXAMPLE 1 ————————

New-SPDocKitSnapshot

Does a full load of the SharePoint farm and creates a snapshot file in the default location (current working directory).


———————— EXAMPLE 2 ————————

New-SPDocKitSnapshot -PersonalSitesOff -DatabasePermissionsOff -threads 8 -location "C:\spdockit\"

    Skips personal sites and does not load database permissions, using 8 threads for parallel load. Saves the snapshot file to "C:\spdockit\" folder.


———————— EXAMPLE 3 ————————

New-SPDocKitSnapshot -noFeats -noUpdates -noIIS -noSQL

    Excludes features and solutions, programs and updates, IIS settings and SQL Server configuration from a load, using aliases instead of full named parameters.


———————— EXAMPLE 4 ————————

New-SPDocKitSnapshot -globalTimeout 3000 -FarmAccessTimeout 500

Sets the server global timeout to 3000 seconds, farm access timeout to 500 seconds and does a full load of the SharePoint farm, saving the snapshot file to the default location (current working directory).
```

