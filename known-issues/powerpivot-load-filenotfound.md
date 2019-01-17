---
title: PowerPivot FileNotFoundException issue
description: >-
  A FileNotFoundException error message keeps appearing during SPDocKit's
  snapshot process.
author: Iva Novoselic
date: 25/5/2017
---

# PowerPivot FileNotFoundException issue

**Summary:** During the snapshot process, the following error can be observed either in the Snapshot Wizard or the event log:

> System.IO.FileLoadException: Could not load file or assembly ‘Microsoft.AnalysisServices.SPAddin, Version=11.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91’ or one of its dependencies. The located assembly’s manifest definition does not match the assembly reference. \(Exception from HRESULT: 0x80131040\)…\`

**Application version:** All versions

**Solution:** Make sure that you take a snapshot on a server where “PowerPivot for SharePoint Add-in” is installed.

If the error still occurs, please do the following:

1. Determine the correct major version \[MajorVersion\] of “PowerPivot for SharePoint Add-in”. You can do this by viewing the installed programs list and locating Microsoft SQL Server PowerPivot for SharePoint.
2. After you have the correct version, open the SPDocKitSnapshotWizard.exe.config file. It is located in the folder together with the .exe file. 
3. Inside the runtime tag, add the following as a child node and save the file:

   ```markup
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">    
    <dependentAssembly>      
    <assemblyIdentity name="Microsoft.AnalysisServices.SPAddin" publicKeyToken="89845DCD8080CC91" culture="neutral" />  
    <bindingRedirect oldVersion="0.0.0.0-[MajorVersion].0.0.0" newVersion="[MajorVersion].0.0.0" />    
    </dependentAssembly>    
    </assemblyBinding>
   ```

4. Restart the wizard.

{% hint style="info" %}
Note: This is only possible if you are using the SPDocKit Snapshot Wizard to perform the load. If you are using the PowerShell Module, unfortunately there is no workaround.
{% endhint %}

