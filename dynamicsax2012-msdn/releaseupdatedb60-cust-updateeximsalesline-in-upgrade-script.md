---
title: ReleaseUpdateDB60_Cust.updateEximSalesLine_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateEximSalesLine_IN Upgrade Script
ms:assetid: af9a2b6f-a4e0-dcaf-f86f-1e1593875812
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686574(v=AX.60)
ms:contentKeyID: 49710528
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateEximSalesLine\_IN Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateEximSalesLine_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the EximSalesLine_IN table. The record IDs of the Incentive scheme group, Exim Ports, Exim Product Group are now stored in place of the IncentiveSchemeGroup, PortId and ProductGroup field values.</p></td>
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
<td><p>Accounts receivable</p></td>
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
<td><p>EximIncentiveSchemeGroup_IN</p></td>
</tr>
<tr class="even">
<td><p>EximPorts_IN</p></td>
</tr>
<tr class="odd">
<td><p>EximProductGroupTable_IN</p></td>
</tr>
<tr class="even">
<td><p>EximSalesLine_IN</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: EximIncentiveSchemeGroup_IN</p></th>
<th><p>To Table: EximSalesLine_IN</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>EximIncentiveSchemeGroup</p></td>
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
<th><p>From Table: EximPorts_IN</p></th>
<th><p>To Table: EximSalesLine_IN</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>EximPorts</p></td>
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
<th><p>From Table: EximProductGroupTable_IN</p></th>
<th><p>To Table: EximSalesLine_IN</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>EximProductGroupTable</p></td>
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
<td><p>EximSalesLine_IN</p></td>
<td><p>EximIncentiveSchemeGroup</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>EximSalesLine_IN</p></td>
<td><p>EximPorts</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>EximSalesLine_IN</p></td>
<td><p>EximProductGroupTable</p></td>
<td><p>RefRecId</p></td>
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
<td><p>EximSalesLine_IN</p></td>
<td><p>del_IncentiveSchemeGroup</p></td>
</tr>
<tr class="even">
<td><p>EximSalesLine_IN</p></td>
<td><p>del_PortId</p></td>
</tr>
<tr class="odd">
<td><p>EximSalesLine_IN</p></td>
<td><p>del_ProductGroup</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

