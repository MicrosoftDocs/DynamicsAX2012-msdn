---
title: ReleaseUpdateDB60_Basic.allowDupRTax25LedgerInterval_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowDupRTax25LedgerInterval_RU Upgrade Script
ms:assetid: f621db58-70ed-8f3a-bd4e-cf29802476fe
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737587(v=AX.60)
ms:contentKeyID: 49712280
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowDupRTax25LedgerInterval\_RU Upgrade Script 


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
<td><p>allowDupRTax25LedgerInterval_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index GroupIdx in the table RTax25LedgerInterval to allow duplicate records.</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>RTax25LedgerInterval</p></td>
</tr>
</tbody>
</table>


## Remarks

The IntervalGroup field is replaced with the new RTax25LedgerIntervalGroup surrogate, key field in the unique index GroupIdx. Initially this field contains no value. So the index is set to allow duplicates before the field is updated with the value of the record ID field of the RTax25LedgerIntervalGroup table.

  


