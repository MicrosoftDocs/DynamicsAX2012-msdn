---
title: ReleaseUpdateTransformDB40_Vend.purchTableDeltaPreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Vend.purchTableDeltaPreUpgradeProcess Upgrade Script
ms:assetid: 8f0c5f7f-f7be-62ce-52ce-62f4467aa061
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736525(v=AX.60)
ms:contentKeyID: 49709714
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Vend.purchTableDeltaPreUpgradeProcess Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>purchTableDeltaPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Recreates the Shadow_PurchTable_Vend records that are not matched to the PurchTable records and sets the reference to the SourceDocumentHeader records.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
</tr>
</tbody>
</table>


## Affected Modules and Tables

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Affected Modules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Accounts payable</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Affected Tables</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SourceDocumentHeader</p></td>
</tr>
<tr class="even">
<td><p>Shadow_PurchTable_Vend</p></td>
</tr>
</tbody>
</table>


## Remarks

The Shadow\_PurchTable\_Vend records must be synched with the PurchTable records, because there could be new records or modified records in the PurchTable table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: SourceDocumentHeader</p></th>
<th><p>To Table: Shadow_PurchTable_Vend</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>SourceDocumentHeader</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PurchTable</p></th>
<th><p>To Table: Shadow_PurchTable_Vend</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>RecVersion</p></td>
<td><p>RecVersionId</p></td>
</tr>
</tbody>
</table>


## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SourceDocumentHeader</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>PurchTable</p></td>
<td><p>SourceDocumentHeader</p></td>
<td><p>RefRecId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

