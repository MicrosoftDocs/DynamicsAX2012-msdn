---
title: ReleaseUpdateDB60_Basic.allowNoDupIntrastatArchiveDetailArchIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowNoDupIntrastatArchiveDetailArchIdx Upgrade Script
ms:assetid: edc89361-6881-2c23-99e9-4f9623337f8f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719974(v=AX.60)
ms:contentKeyID: 49712046
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowNoDupIntrastatArchiveDetailArchIdx Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupIntrastatArchiveDetailArchIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index ArchIdx in the table IntrastatArchiveDetail not to allow duplicate records.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>IntrastatArchiveDetail</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the surrogate key field IntrastatArchiveGeneral with the value of the record ID field of the IntrastatArchiveGeneral table, the ArchIdx index is reset not to allow duplicate records.

  


