---
title: Snapshots Screen
description: This article states how to use Snapshots Screen an track changes made to your SharePoint farm during its lifetime.
author: Tomislav Sirovec
date: 23/6/2018
---
The __Snapshots Screen__ allows SharePoint administrators to track changes made to the SharePoint Farm during its lifetime. The snapshots contain information about all the [settings SPDocKit can retrieve](#internal/how-to/sharepoint-farm-snapshots/manual-snapshots).

This screen will display snapshots found in SPDocKit database and snapshots folder on a disk and group them by the farm they were created on:
* __Blue icon__ indicates that the snapshot is stored in a SPDocKit database. 
* __Green icon__ means that the snapshot is saved in the snapshot folder (on the disk).
* __Bolded__ snapshot name means that the snapshot is currently selected/opened. 

The following commands are available:

* __Open__ – open currently selected snapshot.
* __Delete__– this button will delete the currently selected snapshot from previously defined snapshot locations. Snapshots saved to a disk location will be deleted only if they are from the local farm. Snapshots saved in the SPDocKit database will be deleted regardless of the farm they are created on.
* __Import__ – use this button to add a snapshot to this list from any other location. Once that the snapshot is imported, it remains here until the user removes it.
* __Export__– use this button to create farm snapshot file which can be transferred to any other location. This comes in handy if your snapshots are stored in SPDocKit database but you need to move them from one server to another.
* __Show Changes__ – shows differences between the currently selected snapshot and an older snapshot (if one exists).
* __Compare Wizard__– starts Compare Wizard for more complex comparisons.
* __Compare to Local__ – compares a snapshot with the currently loaded local farm.
* __Compare Selected__  – if two snapshots are selected, this button compares SharePoint settings stored in these two.
* __Mark Configuration as Good__ – use this button to mark which SPDocKit snapshot captured your SharePoint farm with all the settings configured in a best possible way. Also, this will exclude that snapshot from data retention policy. Meaning, it will not be deleted.
* __Rename Farm__ - if you store snapshots from more than one farm, this option allows you to change a default farm name for easier distinction. This option will work only if snapshots are stored in SPDocKit database.
* __File Name__ – to activate this column go to the __View__ tab and use the __Choose Columns__ button. For more information on how to change the default file name [see here](#internal/get-to-know-spdockit/backstage-screen/options-wizard#snapshot-options) and observe the snapshots name template section.
* __Load Duration__ - this column displays how long it took to take a snapshot of your environment.
