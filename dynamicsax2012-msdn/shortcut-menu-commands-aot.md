---
title: 'Shortcut Menu Commands: AOT'
TOCTitle: 'Shortcut Menu Commands: AOT'
ms:assetid: 9b842089-d0d5-4d0a-a3a3-73d976f689e5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa846291(v=AX.60)
ms:contentKeyID: 35248183
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Shortcut Menu Commands: AOT [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In the Application Object Tree (AOT) in Microsoft Dynamics AX, there are many development commands available on the shortcut menu that depends on the node that you select. This topic lists and describes the shortcut menu commands in alphabetical order.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Command</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Add-Ins</strong></p></td>
<td><p>Opens the <strong>Add-Ins</strong> submenu. This menu contains development tools. For example, the cross-reference system and compare feature. For more information, see <a href="add-ins-submenu.md">Add-Ins Submenu</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Add to Version Control</strong></p></td>
<td><p>When version control is enabled, this command lets you add a new element to the version control system. For more information, see <a href="how-to-set-up-local-version-control-parameters-developer.md">How to: Set Up Local Version Control Parameters (Developer)</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Add reference</strong></p></td>
<td><p>Opens the <strong>Add reference</strong> dialog box to let you browse or select a reference to a .NET assembly.</p></td>
</tr>
<tr class="even">
<td><p><strong>Check In</strong></p></td>
<td><p>When version control is enabled, this command lets you check an element into the version control system. For more information, see <a href="version-control-system.md">Version Control System</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Check Out</strong></p></td>
<td><p>When version control is enabled, this command lets you check out the selected element from the version control system. This command is only available after an element has been checked into the version control system. For more information, see <a href="version-control-system.md">Version Control System</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Compare</strong></p></td>
<td><p>Enables you to compare the selected element together with another element or with another version of the same element. For more information, see <a href="compare-tool.md">Compare Tool</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Compile</strong></p></td>
<td><p>Enables you to compile a method or a subtree.</p>
<p>When you exit the code editor without compiling (or saving), the system automatically compiles (or saves) the method.</p></td>
</tr>
<tr class="even">
<td><p><strong>Copy</strong></p></td>
<td><p>Creates a copy of the selected element.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Delete</strong></p></td>
<td><p>Deletes the selected element.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Hh404129.alert_caution(en-us,AX.60).gif" title="Caution note" alt="Caution note" class="note" /><strong>Caution</strong>
</div>
<div class="mtps-row">
Use <strong>Delete</strong> with caution. Elements cannot be recovered after they have been deleted.
</div>
</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy Element</strong></p></td>
<td><p>Deploys the selected element.</p></td>
</tr>
<tr class="odd">
<td><p>Deploy to EP</p></td>
<td><p>Deploys the selected element to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p><strong>Duplicate</strong></p></td>
<td><p>Creates a copy of the selected element.</p></td>
</tr>
<tr class="odd">
<td><p><strong>View code</strong></p></td>
<td><p>Opens an element in the code editor.</p></td>
</tr>
<tr class="even">
<td><p><strong>Export</strong></p></td>
<td><p>Extracts code from the system to an .xpo file. For more information, see <a href="how-to-export-application-objects-by-using-the-aot.md">How to: Export Application Objects by Using the AOT</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Find</strong></p></td>
<td><p>Enables you to locate an element in the AOT.</p></td>
</tr>
<tr class="even">
<td><p><strong>Generate Design</strong></p></td>
<td><p>Generates a report design based on the query structure.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Generate Specs From Query</strong></p></td>
<td><p>Generates a design structure similar to the data source structure in the query.</p></td>
</tr>
<tr class="even">
<td><p><strong>History</strong></p></td>
<td><p>When version control is enabled, this command allows you to open the <strong>History</strong> form. The <strong>History</strong> form enables you to see the check-in comments for each version of an element and the identity of the developer who made the changes. For more information, see <a href="how-to-view-the-history-of-an-element.md">How to: View the History of an Element</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>New</strong> &lt;element name&gt;</p></td>
<td><p>Creates a new element in the selected AOT node.</p></td>
</tr>
<tr class="even">
<td><p><strong>Open</strong></p></td>
<td><p>Opens the selected element.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Open New Window</strong></p></td>
<td><p>Creates a new window with the selected node and its subnodes. The selected node becomes the root of the new tree structure.</p></td>
</tr>
<tr class="even">
<td><p><strong>Override Method</strong></p></td>
<td><p>Enables you to select a method to override.</p>
<p>When you create a new element of type class, table, or form, several methods are created by the system. These methods call super(), executing the system implementation of the method. You can add you own code to the methods, overriding the standard behavior of the system. For classes, the super class methods that can be overridden are also shown. For more information, see <a href="overriding-a-method.md">Overriding a Method</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Page Formatting</strong></p></td>
<td><p>Enables you to set up the page formatting for a report.</p></td>
</tr>
<tr class="even">
<td><p><strong>Paste</strong></p></td>
<td><p>Inserts the element you have previously copied.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Printer Setup</strong></p></td>
<td><p>Enables you to set up your report printer.</p></td>
</tr>
<tr class="even">
<td><p><strong>Properties</strong></p></td>
<td><p>Opens the <strong>Properties</strong> sheet for the selected element.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Refresh</strong></p></td>
<td><p>Updates the list of elements.</p>
<p>To update the contents of the elements, use the <strong>Restore</strong> command.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rename</strong></p></td>
<td><p>Enables you to rename the selected element.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Tip" alt="Tip" class="note" /><strong>Tip</strong>
</div>
<div class="mtps-row">
You can also rename an element in the <strong>Property</strong> sheet or by double-clicking the element.
</div>
</div></td>
</tr>
<tr class="odd">
<td><p><strong>Restore</strong></p></td>
<td><p>Reads the selected element from the database and discards the changes that were made since the last save.</p></td>
</tr>
<tr class="even">
<td><p><strong>Save</strong></p></td>
<td><p>Commits the selected element to the database.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Synchronize</strong></p></td>
<td><p>Synchronizes the database.</p></td>
</tr>
<tr class="even">
<td><p><strong>Undo Check Out</strong></p></td>
<td><p>Reverts to the version of the element that you checked out (this enables you to check the element back in without any of the changes you made after checking it out). For more information, see <a href="how-to-set-up-local-version-control-parameters-developer.md">How to: Set Up Local Version Control Parameters (Developer)</a>.</p></td>
</tr>
</tbody>
</table>


## See also

[Add-Ins Submenu](add-ins-submenu.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

