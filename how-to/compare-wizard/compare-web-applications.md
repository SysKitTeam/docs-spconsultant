---
title: Compare Web Applications
description: >-
  This section describes how to use SPDocKit to compare SharePoint farm web
  application configurations.
author: Tomislav Sirovec
date: 18/6/2018
---

# Compare Web Applications

This section describes how to use SPDocKit to compare SharePoint farm **web application** configurations.

You can use this wizard to:

* Examine the web application’s configuration in relation to another SharePoint web application.
* Compare SharePoint Web Application configurations for the entire history by selecting the same SharePoint web application in a different time period.

Here is how to do it:

1. Navigate to the **Backstage Actions Screen** and click **Compare Wizard** button.
2. Select **Web Applications** for the comparison type. Click **Next** to continue.
3. If you would like to compare two different web application settings for a specific date, selecting just one snapshot is sufficient.

   If you would like to compare the same web application but at different points in time, select two snapshots that correspond to the time period you would like to track changes to.

   The Farm selection step will list all available snapshots. If the desired snapshot is not located here, click **Import** to select a snapshot file from another location. Importing snapshots is a one-time action, so the next time you run the Compare Wizard you will have to repeat the process. If you would like to [import these snapshots permanently](https://github.com/SysKitTeam/docs-spconsultant/tree/9e13d429248cbcbda970f6080d09ff6d6f31d812/compare-wizard/c../get-to-know-spdockit/snapshots-screen.md), click **Import** in the Snapshots tab.

4. In the Compare results dialog box, you can see the web applications overview. To compare, specify your web application **Source** on the left-hand side, and the **Target** on the right-hand side.

