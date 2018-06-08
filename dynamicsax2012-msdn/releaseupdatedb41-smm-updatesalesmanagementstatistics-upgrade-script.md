---
title: ReleaseUpdateDB41_smm.updateSalesManagementStatistics Upgrade Script
TOCTitle: ReleaseUpdateDB41_smm.updateSalesManagementStatistics Upgrade Script
ms:assetid: 09bc8b51-e482-68b3-167f-2cc5be0d9106
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735597(v=AX.60)
ms:contentKeyID: 49706507
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_smm.updateSalesManagementStatistics Upgrade Script 


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
<td><p>updateSalesManagementStatistics</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Replaces removed fields from the SalesQuotation in the management statistics table. Deletes obsolete fields from the AllowedFields. Replaces old Date fields with DateTime fields from the AllowedFields. Replaces old Date values with DateTime values from the Graph table. Replaces the query with reference to old Date fields with new DateTime field.</p></td>
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
<td><p>smmSalesManagementAllowedFields</p></td>
</tr>
<tr class="even">
<td><p>smmSalesManagementGraphOptions</p></td>
</tr>
<tr class="odd">
<td><p>smmSalesManagementGraphTable</p></td>
</tr>
<tr class="even">
<td><p>smmSalesManagementQueriesTable</p></td>
</tr>
<tr class="odd">
<td><p>SysInfolog</p></td>
</tr>
</tbody>
</table>


## Remarks

Replaces removed fields from the SalesQuotation in the management statistics table. Deletes obsolete fields from the AllowedFields. Replaces old Date fields with DateTime fields from the AllowedFields. Replaces old Date values with DateTime values from Graph table. Replaces the query with reference to old Date fields with new DateTime fields.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

