---
title: Compare SharePoint Farms
description: This section explains how you can use the Compare Wizard to compare different farms or snapshots of an existing farm.
author: Tomislav Sirovec
date: 30/6/2018
---
This section explains how you can use the Compare Wizard to compare different farms or snapshots of an existing farm. Navigate to the Backstage Actions Screen and click the __Compare Wizard__ button.

### Compare farm with a previous snapshot

1. Select Farms as the comparison type and then the __Compare farm with a previous farm snapshot__ subtype. Click Next to continue. 

1. Under the __Farm Selection__, you can select different, previously taken snapshots and compare them. 

   The Farm selection step will list all available snapshots from the. If the desired snapshot is not located here, click __Import__ to select a snapshot file from another location. Importing snapshots is a one-time action, so the next time you run the Compare Wizard you will have to repeat the process. If you would like to [import these snapshots permanently](#internal/get-to-know-spdockit/snapshots-screen), click __Import__ in the Snapshots tab.

1. Click Next to see the farm compare results.

    The Results windows shows the differences between two farm snapshots.
    Object changes are marked by a different colors. The upper part of the window shows all farm settings in a hierarchical structure, while the bottom half displays the differences between currently selected objects in the upper half.

    Farm compare uses the [Compare template](#internal/get-to-know-spdockit/backstage-screen/options-wizard/#compare) when displaying changes between snapshots.  If you would like to change which reports are compared, use the little wheel button on the left-hand side. Deselected reports will not be used in future comparisons.


### Compare two different SharePoint farms
1. Select Farms as the comparison type and then the __Compare two different farms__ subtype. Click Next to continue.

1. Under __Farm Selection__, select the snapshots you wish to compare and click Next.

  The Farm selection step will list all available snapshots. If the desired snapshot is not located here, click __Import__ to select a snapshot file from another location. Importing snapshots is a one-time action, so the next time you run the Compare Wizard you will have to repeat the process. If you would like to [import these snapshots permanently](#internal/get-to-know-spdockit/snapshots-screen), click __Import__ in the Snapshots tab.

1. The next couple of steps allow you to map the properties of the two farms and perform a detailed comparisons. Grids will be displayed to allow you to map farm servers, accounts, service applications, and more, from one farm to the other. Use the drop down menu to define which farm properties should be paired. Once you have paired them, SPDocKit will remember the mappings you specified and reuse them for each subsequent comparison between these two farms.

    __1:N mappings__ between properties is enabled. This can be very useful when comparing test with production environments. For example, you can map servers on a test farm, which contains only a few servers, multiple times to servers from a much larger production farm.
    
    The wizard will guide you through the following mappings:
    * URLs, Host Headers, Addresses
    * Database Names
    * Business Data Connectivity Namespace
    * Farm Servers
    * SQL Servers
    * Accounts (service accounts, managed accounts, user policy accounts, search accounts, application pool accounts, object cache accounts, farm administrators, service application administrator accounts)
    * Service Applications
    * Service Applications Proxies
    * Host Names

1. Click Next to see the compare results.

    The Results windows shows the differences between two farm snapshots.
    Object changes are marked by a different colors. The upper part of the window shows all farm settings in a hierarchical structure, while the bottom half displays the differences between currently selected objects in the upper half.

    Farm compare uses the [Compare template](#internal/get-to-know-spdockit/backstage-screen/options-wizard/#compare) when displaying changes between snapshots. If you would like to change which reports are compared, use the little wheel button on the left-hand side. Deselected reports will not be used in future comparisons.

### Compare with out of the box farm
1. Select Farms for the comparison type and then the __Compare with out of the box farm__ subtype to continue the process.

1. Under __Farm Selection__, select the snapshot you wish to compare with default farm settings and click Next.

1. The compare results will appear. 
  
   Farm compare uses the [Compare template](#internal/get-to-know-spdockit/backstage-screen/options-wizard/#compare) when displaying changes between snapshots. If you would like to change which reports are compared, use the little wheel button on the left-hand side. Deselected reports will not be used in future comparisons.
