---
title: ReleaseUpdateDB60_Jmg.updateJmgClientFieldTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Jmg.updateJmgClientFieldTable Upgrade Script
ms:assetid: bd4ff811-1c0a-87c2-c86b-3ab52d5b5cff
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686679(v=AX.60)
ms:contentKeyID: 49710877
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Jmg.updateJmgClientFieldTable Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Jmg</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateJmgClientFieldTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the JmgRegistrationSetup table, JmgClientFieldTable table and JmgRegistrationGridTable table to support the new grid system for the registration client.</p></td>
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
<td><p>Shop Floor Control</p></td>
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
<td><p>JmgRegistrationSetup</p></td>
</tr>
<tr class="even">
<td><p>JmgClientFieldTable</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationGridTable</p></td>
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
<td><p>JmgClientFieldTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationGridTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>ProjGridSetupId</p></td>
<td><p>JmgGridSetupRecId</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationSetup</p></td>
<td><p>IPCGridSetupId</p></td>
<td><p>JmgGridSetupRecId</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>ProdGridSetupId</p></td>
<td><p>JmgGridSetupRecId</p></td>
</tr>
</tbody>
</table>

  


