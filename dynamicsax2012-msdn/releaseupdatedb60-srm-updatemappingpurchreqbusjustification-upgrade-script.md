﻿---
title: ReleaseUpdateDB60_Srm.updateMappingPurchReqBusJustification Upgrade Script
TOCTitle: ReleaseUpdateDB60_Srm.updateMappingPurchReqBusJustification Upgrade Script
ms:assetid: 3e069a0d-4a54-6542-bb2b-5145b3b8747a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718756(v=AX.60)
ms:contentKeyID: 49707799
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Srm.updateMappingPurchReqBusJustification Upgrade Script [AX 2012]


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
<td><p>updateMappingPurchReqBusJustification</p></td>
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
<td><p>PurchReqBusJustification</p></td>
</tr>
</tbody>
</table>


## Remarks

The SaveDataPerCompany property of the PurchReqBusJustification table has been set to "No" in this release. This method maps the dataAreaId value to the DEL\_DataAreaId value to preserve the old values.

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
<td><p>PurchReqBusJustification</p></td>
<td><p>DEL_DataAreaId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

