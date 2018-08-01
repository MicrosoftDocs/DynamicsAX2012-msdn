---
title: ReleaseUpdateDB41_smm.updateCustomerColumns Upgrade Script
TOCTitle: ReleaseUpdateDB41_smm.updateCustomerColumns Upgrade Script
ms:assetid: d11952dd-dc3e-8818-2e60-19323d1f0056
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686919(v=AX.60)
ms:contentKeyID: 49711369
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_smm.updateCustomerColumns Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_smm</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCustomerColumns</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies the data from the smmBusRelTable table to the CusTable for each of the new fields that are introduced to those tables.</p></td>
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
<td><p>smm</p></td>
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
<td><p>CustTable</p></td>
</tr>
<tr class="even">
<td><p>smmBusRelTable</p></td>
</tr>
<tr class="odd">
<td><p>SysInfolog</p></td>
</tr>
</tbody>
</table>


## Remarks

This method copies the data from the smmBusRelTable field to the CusTable table for each of the new fields that are introduced to those tables.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

