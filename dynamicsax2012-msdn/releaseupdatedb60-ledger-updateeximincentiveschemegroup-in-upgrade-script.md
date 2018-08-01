---
title: ReleaseUpdateDB60_Ledger.updateEximIncentiveSchemeGroup_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateEximIncentiveSchemeGroup_IN Upgrade Script
ms:assetid: a47decdf-d3fa-d601-bcaa-8c5d085f5828
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736813(v=AX.60)
ms:contentKeyID: 49710244
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateEximIncentiveSchemeGroup\_IN Upgrade Script 


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
<td><p>updateEximIncentiveSchemeGroup_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the EximIncentiveSchemeGroup_IN table. The record ID of the EximPorts_IN table is now stored in place of the PortId value.</p></td>
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
<th><p>From Table: EximPorts_IN</p></th>
<th><p>To Table: EximIncentiveSchemeGroup_IN</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>EximPortId</p></td>
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
<td><p>EximIncentiveSchemeGroup_IN</p></td>
<td><p>EximPortId</p></td>
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
<td><p>EximIncentiveSchemeGroup_IN</p></td>
<td><p>DEL_PortId</p></td>
</tr>
</tbody>
</table>

  


