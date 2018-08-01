---
title: ReleaseUpdateDB60_Vend.updateVendReasonCodes Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendReasonCodes Upgrade Script
ms:assetid: d8b41365-7697-7921-521f-32f8ac3ca4a9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687102(v=AX.60)
ms:contentKeyID: 49711550
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendReasonCodes Upgrade Script 


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
<td><p>updateVendReasonCodes</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Merges reason records from the PurchRFQReasonCode table into the ReasonTable table, and updates related tables.</p></td>
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

The reason ID in the PurchRFQReasonCode table has a length of twenty characters, and truncation logic ensures that unique reason IDs will be assigned. The reason ID will be assigned to the ReasonTable.ReasonId field. If it is larger than ten characters, it will be truncated to ten characters. If it does not exist in the ReasonTable table, the assigned ID will be used. If the assigned reason ID already exists in the ReasonTable with the same description, then the Vend property will be set to true if it is false. If the reason ID is matched to a reason ID with a different description, a new reason ID will be assigned by truncating the ID to seven characters, and combining it with a tilde and a unique numeric value. A record that has the assigned ID, the original description and the Vend property of true is inserted into the ReasonTable table. Once a valid reason ID is assigned, the updateReasonCodeReferences method will be called to update the new reason code reference in the VendRFQJour, PurchRFQTable, PurchRFQLine, VendRFQTrans, and ReasonTableRef tables.

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


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PurchRFQReasonCode</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


