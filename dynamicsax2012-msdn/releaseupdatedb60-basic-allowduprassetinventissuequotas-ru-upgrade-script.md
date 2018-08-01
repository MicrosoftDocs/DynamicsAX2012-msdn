---
title: ReleaseUpdateDB60_Basic.allowDupRAssetInventIssueQuotas_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowDupRAssetInventIssueQuotas_RU Upgrade Script
ms:assetid: 8adf021a-8689-12e5-cdb7-406ff5386f10
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736410(v=AX.60)
ms:contentKeyID: 49709600
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowDupRAssetInventIssueQuotas\_RU Upgrade Script 


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
<td><p>allowDupRAssetInventIssueQuotas_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index QuotasIdx in the table RAssetInventIssueQuotas to allow duplicate records.</p></td>
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
<td><p>RAssetInventIssueQuotas</p></td>
</tr>
</tbody>
</table>


## Remarks

The QuotaTypeId field is replaced with the new QuotaTypesRecId surrogate key field in the QuotasIdx unique index. Initially this field contains no value. So the index is set to allow duplicates before the field is updated with the value of the record ID field of the RAssetInventIssueQuotaTypes table.

  


