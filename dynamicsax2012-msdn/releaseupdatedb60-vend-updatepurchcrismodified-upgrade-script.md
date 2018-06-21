---
title: ReleaseUpdateDB60_Vend.updatePurchCRisModified Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updatePurchCRisModified Upgrade Script
ms:assetid: 44d415c8-ee11-e0bd-0d19-8546446e4f84
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718921(v=AX.60)
ms:contentKeyID: 49707947
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updatePurchCRisModified Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePurchCRisModified</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Sets the new PurchTable.DocumentState attribute to the VersioningDocumentState::Approved enumeration value for all existing Purchase Orders. Marks existing records that compose a Purchase Order with the new IsModified attribute equal to the Yes value.</p></td>
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
<td><p>PurchTable</p></td>
</tr>
<tr class="even">
<td><p>PurchLine</p></td>
</tr>
<tr class="odd">
<td><p>MarkupTrans</p></td>
</tr>
<tr class="even">
<td><p>VendPaymSched</p></td>
</tr>
<tr class="odd">
<td><p>VendPaymSchedLine</p></td>
</tr>
</tbody>
</table>


## Remarks

The script handles all company accounts in one process, of type Shared, and uses a UPDATE %1 command in direct SQL. The manipulation of the MarkupTrans, VendPaymSched, and VendPaymSchedLine tables is limited to records that are related to a Purchase Order.

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
<td><p>PurchTable</p></td>
<td><p>DocumentState</p></td>
<td><p>VersioningDocumentState</p></td>
</tr>
<tr class="even">
<td><p>PurchTable</p></td>
<td><p>IsModfied</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="odd">
<td><p>PurchLine</p></td>
<td><p>IsModified</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="even">
<td><p>MarkupTrans</p></td>
<td><p>IsModified</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="odd">
<td><p>VendPaymSched</p></td>
<td><p>IsModified</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="even">
<td><p>VendPaymSchedLine</p></td>
<td><p>IsModified</p></td>
<td><p>NoYes</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

