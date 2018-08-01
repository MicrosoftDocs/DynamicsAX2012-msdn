---
title: ReleaseUpdateDB41_smm.updateSalesManagementStatistics
TOCTitle: ReleaseUpdateDB41_smm.updateSalesManagementStatistics
ms:assetid: 47fc7ed4-b306-57e8-fd74-654a482e9c9a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685319(v=AX.60)
ms:contentKeyID: 49708014
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_smm.updateSalesManagementStatistics 


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
<td><p>Replaces the removed fields from SalesQuotation in the Management Statistics table.</p>
<p>Deletes the obsolete values from the AllowedFields.</p>
<p>Replaces old Date fields with DateTime fields from the AllowedFields.</p>
<p>Replaces the old Date values with DateTime values from the Graph table.</p>
<p>Replaces the query with references to the old Date fields and replaces it with the new DateTime fields.</p></td>
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

  


