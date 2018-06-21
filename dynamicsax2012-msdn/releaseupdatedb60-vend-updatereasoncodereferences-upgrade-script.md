---
title: ReleaseUpdateDB60_Vend.updateReasonCodeReferences Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateReasonCodeReferences Upgrade Script
ms:assetid: 90b2ec94-63a0-09f6-fdd1-ea91897db03d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736568(v=AX.60)
ms:contentKeyID: 49709757
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateReasonCodeReferences Upgrade Script [AX 2012]


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
<td><p>updateReasonCodeReferences</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates reason code references in the VendRFQJour, purchRFQTable, purchRFQLine, and vendRFQTrans tables.</p></td>
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
<td><p>VendRFQJour</p></td>
</tr>
<tr class="even">
<td><p>VendRFQTrans</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQTable</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQLine</p></td>
</tr>
<tr class="odd">
<td><p>ReasonTableRef</p></td>
</tr>
</tbody>
</table>


## Remarks

The input parameters are the reason code, a comment and the new reason code. This method processes the VendRFQJour, purchRFQTable, PurchRFQLine, and VendRFQTrans tables as follows. Records where the reason code exists and the reason reference field is zero will be selected. A record will be inserted into the ReasonTableRef table with the new reason ID and the comment. The new RecId value from the ReasonTableRef table will be used to update the reason reference field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PurchRFQReasonCode</p></th>
<th><p>To Table: ReasonTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
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
<td><p>VendRFQJour</p></td>
<td><p>ReasonRef</p></td>
<td><p>RecId</p></td>
</tr>
<tr class="even">
<td><p>VendRFQTrans</p></td>
<td><p>ReasonRef</p></td>
<td><p>RecId</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQTable</p></td>
<td><p>ReasonRef</p></td>
<td><p>RecId</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQLine</p></td>
<td><p>ReasonRef</p></td>
<td><p>RecId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

