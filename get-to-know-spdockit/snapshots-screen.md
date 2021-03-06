---
description: This article states how to use Snapshots Screen and track changes made to your SharePoint farm during its lifetime.
---

# Snapshots Screen

The **Snapshots Screen** allows SharePoint administrators to track changes made to the SharePoint Farm during its lifetime. The snapshots contain information about all the [settings SPDocKit Consultant can retrieve](../how-to/create-snapshot.md).

This screen will display snapshots found in snapshots folder on a disk and group them by the farm they were created on:

* **Green icon** means that the snapshot is saved in the snapshot folder \(on the disk\).
* **Bolded** snapshot name means that the snapshot is currently selected/opened. 

The following commands are available:

* **Open** – open currently selected snapshot.
* **Delete**– this button will delete the currently selected snapshot from previously defined snapshot locations.
* **Import** – use this button to add a snapshot to this list from any other location. Once that the snapshot is imported, it remains here until the user removes it.
* **Export**– use this button to create farm snapshot file which can be transferred to any other location. 
* **Show Changes** – shows differences between the currently selected snapshot and an older snapshot \(if one exists\).
* **Compare Wizard**– starts Compare Wizard for more complex comparisons.
* **Compare to Local** – compares a snapshot with the currently loaded local farm.
* **Compare Selected**  – if two snapshots are selected, this button compares SharePoint settings stored in these two.
* **Mark Configuration as Good** – use this button to mark which SPDocKit Consultant snapshot captured your SharePoint farm with all the settings configured in a best possible way. Also, this will exclude that snapshot from data retention policy. Meaning, it will not be deleted.
* **Rename Farm** - if you store snapshots from more than one farm, this option allows you to change a default farm name for easier distinction. 
* **File Name** – to activate this column go to the **View** tab and use the **Choose Columns** button. For more information on how to change the default file name [see here](backstage-screen/options-wizard.md#snapshot-options) and observe the snapshots name template section.
* **Load Duration** - this column displays how long it took to take a snapshot of your environment.

