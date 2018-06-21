---
title: Viewing the Cross-Reference System Information
TOCTitle: Viewing the Cross-Reference System Information
ms:assetid: a2851e6b-56ab-4461-b639-e4395ecb312a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa849569(v=AX.60)
ms:contentKeyID: 35248344
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Viewing the Cross-Reference System Information [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you have [generated your cross-reference information](how-to-create-the-cross-reference-system.md), you can access information from the Application Object Tree (AOT), or from the Tools menu.

  - Use the AOT to view cross-reference information for a particular object.

  - Use the Tools menu for an overview of information about all objects.

## Options Available from the AOT

If you right-click on an object in the AOT and select **Add-Ins** \> **Cross-reference**, there are a number of options:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Option</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Used by</p></td>
<td><p>Displays the objects that use the current object.</p></td>
</tr>
<tr class="even">
<td><p>Using (instant view)</p></td>
<td><p>Displays the objects that the current object uses.</p></td>
</tr>
</tbody>
</table>


These options are not available for every kind of application object. Options can also be absent if the cross-reference system does not exist or is out of date, or if, for example, the object is not used by any other object.

## Options Available from the Tools Menu

The following options are available from **Tools** \>**Cross-reference**:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Option</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Names</p></td>
<td><p>Lists all the objects in the cross-reference system, with the number of references in the cross-reference system.</p>
<p>You can use the form to see which objects use a particular object (used by a button).</p></td>
</tr>
<tr class="even">
<td><p>Paths</p></td>
<td><p>Shows the location in the AOT of all objects in the cross-reference system, the number of references, the time when the cross-references for an object were last updated, and whether the object is still valid (deleted objects are not automatically removed from the cross-reference system).</p>
<p>You can use the form to see which objects a particular object uses (Using button).</p></td>
</tr>
<tr class="odd">
<td><p>Reports &gt; Names/Uses</p></td>
<td><p>Generates a report about objects in the cross reference system to show: object names, object types and paths, and the type of action on the object (for example read, write, declaration, definition, or call).</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Tip" alt="Tip" class="note" /><strong>Tip</strong>
</div>
<div class="mtps-row">
To avoid generating a huge report you should always select criteria. You can interrupt the report generation with CTRL+BREAK.
</div>
</div></td>
</tr>
</tbody>
</table>

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

