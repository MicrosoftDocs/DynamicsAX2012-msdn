---
title: ReleaseUpdateDB60_Srm.updateMappingPurchReqTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Srm.updateMappingPurchReqTable Upgrade Script
ms:assetid: 1e5fd4d7-b06b-f1c1-7e85-832f5724d7ed
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684838(v=AX.60)
ms:contentKeyID: 49707041
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Srm.updateMappingPurchReqTable Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Srm</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateMappingPurchReqTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Maps field DataAreaId to DEL_dataAreaId.</p></td>
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
<td><p>PurchReqTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The SaveDataPerCompany property of the PurchReqTable table has been set to "No" in this release. This method maps the dataAreaId value to the DEL\_DataAreaId value to preserve the old values.

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
<td><p>PurchReqTable</p></td>
<td><p>DEL_DataAreaId</p></td>
</tr>
</tbody>
</table>

  


