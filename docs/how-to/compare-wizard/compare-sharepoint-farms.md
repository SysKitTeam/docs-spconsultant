---
description: This section explains how you can use the Compare Wizard to compare different farms or snapshots of an existing farm.
---

# Compare Farms

Navigate to the Backstage Actions Screen and click the **Compare Wizard** button.

## Compare farm with a previous snapshot

1. Select Farms as the comparison type and then the **Compare farm with a previous farm snapshot** subtype. Click Next to continue.
2. Under the **Farm Selection**, you can select different, previously taken snapshots and compare them.

   The Farm selection step will list all available snapshots from the. If the desired snapshot is not located here, click **Import** to select a snapshot file from another location. Importing snapshots is a one-time action, so the next time you run the Compare Wizard you will have to repeat the process. If you would like to [import these snapshots permanently](../../get-to-know-spdockit/snapshots-screen.md), click **Import** in the Snapshots tab.

3. Click Next to see the farm compare results.

   The Results windows shows the differences between two farm snapshots. Object changes are marked by a different colors. The upper part of the window shows all farm settings in a hierarchical structure, while the bottom half displays the differences between currently selected objects in the upper half.

   Farm compare uses the [Compare template](../../get-to-know-spdockit/backstage-screen/options-wizard.md#compare) when displaying changes between snapshots. If you would like to change which reports are compared, use the little wheel button on the left-hand side. Deselected reports will not be used in future comparisons.

## Compare two different SharePoint farms

1. Select Farms as the comparison type and then the **Compare two different farms** subtype. Click Next to continue.
2. Under **Farm Selection**, select the snapshots you wish to compare and click Next.

   The Farm selection step will list all available snapshots. If the desired snapshot is not located here, click **Import** to select a snapshot file from another location. Importing snapshots is a one-time action, so the next time you run the Compare Wizard you will have to repeat the process. If you would like to [import these snapshots permanently](../../get-to-know-spdockit/snapshots-screen.md), click **Import** in the Snapshots tab.

3. The next couple of steps allow you to map the properties of the two farms and perform a detailed comparisons. Grids will be displayed to allow you to map farm servers, accounts, service applications, and more, from one farm to the other. Use the drop down menu to define which farm properties should be paired. Once you have paired them, SPDocKit Consultant will remember the mappings you specified and reuse them for each subsequent comparison between these two farms.

   **1:N mappings** between properties is enabled. This can be very useful when comparing test with production environments. For example, you can map servers on a test farm, which contains only a few servers, multiple times to servers from a much larger production farm.

   The wizard will guide you through the following mappings:

   * URLs, Host Headers, Addresses
   * Database Names
   * Business Data Connectivity Namespace
   * Farm Servers
   * SQL Servers
   * Accounts \(service accounts, managed accounts, user policy accounts, search accounts, application pool accounts, object cache accounts, farm administrators, service application administrator accounts\)
   * Service Applications
   * Service Applications Proxies
   * Host Names

4. Click Next to see the compare results.

   The Results windows shows the differences between two farm snapshots. Object changes are marked by a different colors. The upper part of the window shows all farm settings in a hierarchical structure, while the bottom half displays the differences between currently selected objects in the upper half.

   Farm compare uses the [Compare template](../../get-to-know-spdockit/backstage-screen/options-wizard.md#compare) when displaying changes between snapshots. If you would like to change which reports are compared, use the little wheel button on the left-hand side. Deselected reports will not be used in future comparisons.

## Compare with out of the box farm

1. Select Farms for the comparison type and then the **Compare with out of the box farm** subtype to continue the process.
2. Under **Farm Selection**, select the snapshot you wish to compare with default farm settings and click Next.
3. The compare results will appear.

   Farm compare uses the [Compare template](../../get-to-know-spdockit/backstage-screen/options-wizard.md#compare) when displaying changes between snapshots. If you would like to change which reports are compared, use the little wheel button on the left-hand side. Deselected reports will not be used in future comparisons.


