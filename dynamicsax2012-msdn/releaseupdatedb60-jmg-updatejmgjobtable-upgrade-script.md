---
title: ReleaseUpdateDB60_Jmg.updateJmgJobTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Jmg.updateJmgJobTable Upgrade Script
ms:assetid: 92632848-f43d-ddb1-6d63-eaaa439d937d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736609(v=AX.60)
ms:contentKeyID: 49709796
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Jmg.updateJmgJobTable Upgrade Script 


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
<td><p>updateJmgJobTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the JmgJobTable table to support the new resource groups. Updates the JmgJobTable table to support the HcmWorker table instead of the EmplTable table .</p></td>
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
<td><p>JmgJobTable</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrResourceGroup</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrTable</p></td>
</tr>
<tr class="even">
<td><p>HcmWorker</p></td>
</tr>
<tr class="odd">
<td><p>EmplTable</p></td>
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
<td><p>JmgJobTable</p></td>
<td><p>ResourceGroup</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>JmgJobTable</p></td>
<td><p>Worker</p></td>
<td><p>JmgWorkerRecId</p></td>
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
<td><p>JmgJobTable</p></td>
<td><p>EmplId</p></td>
</tr>
<tr class="even">
<td><p>JmgJobTable</p></td>
<td><p>WrkCtrGroupId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

