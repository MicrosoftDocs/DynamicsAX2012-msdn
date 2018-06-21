---
title: ReleaseUpdateDB60_Trv.updateFieldMappingForRenamedFields Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateFieldMappingForRenamedFields Upgrade Script
ms:assetid: 69650195-de98-9d48-3b22-7032b1e5b7f9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685629(v=AX.60)
ms:contentKeyID: 49708831
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateFieldMappingForRenamedFields Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Trv</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateFieldMappingForRenamedFields</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Adds special field mappings for the TrvExpTrans_Proj table.</p></td>
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
<td><p>Expense management</p></td>
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
<td><p>ReleaseUpdateSpecialFieldMapping</p></td>
</tr>
</tbody>
</table>


## Remarks

This method adds a field mapping for the TrvExpTrans\_Proj table, to support the renaming of the RefRecId field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TrvExpTrans_Proj</p></th>
<th><p>To Table: TrvExpTrans_Proj</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RefRecId</p></td>
<td><p>TrvExpTrans</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

