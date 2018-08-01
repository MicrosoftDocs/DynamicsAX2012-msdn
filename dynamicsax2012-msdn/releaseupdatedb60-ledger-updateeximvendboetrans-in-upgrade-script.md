---
title: ReleaseUpdateDB60_Ledger.updateEximVendBOETrans_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateEximVendBOETrans_IN Upgrade Script
ms:assetid: c877a372-9ec2-4f29-f876-d581f366ff27
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719601(v=AX.60)
ms:contentKeyID: 49711168
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateEximVendBOETrans\_IN Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateEximVendBOETrans_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the EximVendBOETrans_IN table. The values of the RecId field of the EximIncentiveSchemeGroup_IN, EximPorts_IN, and EximProductGroupTable_IN tables are now stored in place of the IncentiveSchemeGroup, PortId, and ProductGroup values.</p></td>
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
<td><p>Ledger</p></td>
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
<td><p>EximVendBOETrans_IN</p></td>
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
<th><p>To Table: EximVendBOETrans_IN</p></th>
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
<th><p>To Table: EximVendBOETrans_IN</p></th>
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
<th><p>To Table: EximVendBOETrans_IN</p></th>
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
<td><p>EximVendBOETrans_IN</p></td>
<td><p>EximIncentiveSchemeGroup</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>EximVendBOETrans_IN</p></td>
<td><p>EximPorts</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>EximVendBOETrans_IN</p></td>
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
<td><p>EximVendBOETrans_IN</p></td>
<td><p>del_IncentiveSchemeGroup</p></td>
</tr>
<tr class="even">
<td><p>EximVendBOETrans_IN</p></td>
<td><p>del_PortId</p></td>
</tr>
<tr class="odd">
<td><p>EximVendBOETrans_IN</p></td>
<td><p>del_ProductGroup</p></td>
</tr>
</tbody>
</table>

  


