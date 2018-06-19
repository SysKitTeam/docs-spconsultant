---
title: Compare Web.Config Files
description: This section describes how to use SPDocKit to compare web.config files across different servers, web applications and web application zones.
author: Tomislav Sirovec    
date: 18/6/2018
---
This section describes how to use SPDocKit to compare web.config files across different servers, Web applications and Web application zones.

1. Navigate to the **Backstage Actions Screen** and click the **Compare Wizard** button.

2. Select **Web.config Files** for the comparison type and click **Next** to continue.

3. If you would like to compare web.config files from two different servers or zones for a specific date, selecting just one snapshot is sufficient.

    If you would like to compare the same web.config file but at different points in time, select two snapshots that correspond to the time period you would like to track changes to.

    The Farm selection step will list all available snapshots. If the desired snapshot is not located here, click __Import__ to select a snapshot file from another location. Importing snapshots is a one-time action, so the next time you run the Compare Wizard you will have to repeat the process. If you would like to [import these snapshots permanently](#internal/get-to-know-spdockit/snapshots-screen), click __Import__ in the Snapshots tab.

4. In the **Compare Results** dialog box, you can adjust the filters such as the **Source** and the **Target** to compare and see the differences (if there are any) between two different web.config files associated with selected Web applications. The differences are highlighted. You can use the buttons to navigate between the files while looking for differences.

SharePoint Web applications can be hosted on multiple servers and can extend into multiple zones. Every server has to have separate web.config files for each zone of every Web application. All web.config files on different servers and the same Web application zone must be equal. Because of these SharePoint requirements, you will also find the filters section in the Comparison Result window.

