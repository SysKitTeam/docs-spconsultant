---
title: Compare Servers
description: >-
  This section explains how you can use the Compare Wizard to compare different
  servers. Including IIS and SQL servers.
author: Tomislav Sirovec
date: 30/6/2018
---

# Compare Servers

Navigate to the Backstage Actions Screen and click the **Compare Wizard** button.

1. Select Servers as the comparison type and then one of the three subtypes. Choose either **IIS Servers**, **SQL Servers** or just **Servers**. Click Next to continue. 
2. Under the **Farm Selection**, you can select different, previously taken snapshots and compare them. You can choose just one snapshot if you wish to compare two different servers but using the same snapshot reference.

   The Farm selection step will list all available snapshots. If the desired snapshot is not located here, click **Import** to select a snapshot file from another location. Importing snapshots is a one-time action, so the next time you run the Compare Wizard you will have to repeat the process. If you would like to [import these snapshots permanently](../../get-to-know-spdockit/snapshots-screen.md), click **Import** in the Snapshots tab.

3. Choose a certain server on both source and target sides. The Results window shows the detected differences marked using different colors. The upper part of the window shows all available farm reports in a hierarchical structure, while the bottom half displays the detected differences between currently selected objects.
   * For **IIS Servers** compare, available reports will be in **Servers in Farm** and **IIS** categories.  
   * For **SQL Servers** compare, available reports will be in **Servers in Farm** and **SQL** categories.  
   * For **Server** compare option, only **Servers in Farm** reports will be available. 

