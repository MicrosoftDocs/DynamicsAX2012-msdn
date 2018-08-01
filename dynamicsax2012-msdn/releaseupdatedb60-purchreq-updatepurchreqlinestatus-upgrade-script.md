---
title: ReleaseUpdateDB60_PurchReq.updatePurchReqLineStatus Upgrade Script
TOCTitle: ReleaseUpdateDB60_PurchReq.updatePurchReqLineStatus Upgrade Script
ms:assetid: 8b23243e-638b-a99b-7f59-372b0db964b4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736421(v=AX.60)
ms:contentKeyID: 49709611
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_PurchReq.updatePurchReqLineStatus Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_PurchReq</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePurchReqLineStatus</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Initializes the value of the Status field in the PurchReqLine table.</p></td>
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
<td><p>SRM</p></td>
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
<td><p>PurchReqLine</p></td>
</tr>
</tbody>
</table>


## Remarks

We have introduced a new field called Status in the PurchReqLine table in this release. This method initializes the value of the new field from the deprecated Status field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PurchReqLine</p></th>
<th><p>To Table: PurchReqLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_Status</p></td>
<td><p>Status</p></td>
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
<td><p>PurchReqLine</p></td>
<td><p>Status</p></td>
<td><p>PurchReqRequisitionStatus</p></td>
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
<td><p>PurchReqLine</p></td>
<td><p>DEL_Status</p></td>
</tr>
</tbody>
</table>

  


