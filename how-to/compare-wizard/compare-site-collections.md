---
title: Compare Site Collections
description: >-
  This sections describes how to use SPDocKit Consultant to compare SharePoint farm site
  collection configurations.
author: Tomislav Sirovec
date: 18/6/2018
---

# Compare Site Collections

This sections describes how to use SPDocKit Consultant to compare SharePoint farm **site collection** configurations.

You can use this wizard to:

* Examine the site collection’s configuration in a relation to another SharePoint site collection.
* Compare SharePoint site collection configuration for the entire history by selecting the same SharePoint site collection in a different time period.

Here is how to do it:

1. Navigate to the **Backstage Actions Screen** and click the **Compare Wizard** button.
2. Select Site Collections for the comparison type. Click **Next** to continue.
3. If you would like to compare two different site collection settings for a specific date, selecting just one snapshot is sufficient.

   If you would like to compare the same site collection settings but at different points in time, select two snapshots that correspond to the time period you would like to track changes to.

   The Farm selection step will list all available snapshots. If the desired snapshot is not located here, click **Import** to select a snapshot file from another location. Importing snapshots is a one-time action, so the next time you run the Compare Wizard you will have to repeat the process. If you would like to [import these snapshots permanently](../../get-to-know-spdockit/snapshots-screen.md), click **Import** in the Snapshots tab.

4. The **Compare Results** dialog box shows the differences between two site collections. The change in each object is indicated by a different color. To compare, specify the **Source** site collection on the left-hand side, as well as the **Target** on the right-hand side.

