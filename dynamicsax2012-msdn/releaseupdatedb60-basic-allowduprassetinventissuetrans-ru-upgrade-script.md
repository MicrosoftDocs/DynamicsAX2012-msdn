---
title: ReleaseUpdateDB60_Basic.allowDupRAssetInventIssueTrans_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowDupRAssetInventIssueTrans_RU Upgrade Script
ms:assetid: f180b654-062f-b85e-06ca-aa9e26d960e8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737430(v=AX.60)
ms:contentKeyID: 49712126
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowDupRAssetInventIssueTrans\_RU Upgrade Script 


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
<td><p>allowDupRAssetInventIssueTrans_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the JournalIdx index in the RAssetInventIssueTrans table to allow duplicate records.</p></td>
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
<td><p>Fixed Asset</p></td>
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
<td><p>RAssetInventIssueTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

The JournalId field is replaced with the InventIssueTableRecId new surrogate, key field in the JournalIdx unique index. Initially this field contains no value. So the index is set to allow duplicates before the field is updated with the value of the record ID field of the RAssetInventIssueTable table.

  


