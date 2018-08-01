---
title: ReleaseUpdateDB60_Basic.allowNoDupRTax25LedgerInterval_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowNoDupRTax25LedgerInterval_RU Upgrade Script
ms:assetid: e5585459-81af-ee3d-8fe2-65a7f3ac4e18
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719778(v=AX.60)
ms:contentKeyID: 49711851
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowNoDupRTax25LedgerInterval\_RU Upgrade Script 


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
<td><p>allowNoDupRTax25LedgerInterval_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the GroupIdx index in the RTax25LedgerInterval table not to allow duplicate records.</p></td>
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

After updating the RTax25LedgerIntervalGroup surrogate key field with the value of the record ID field of the RTax25LedgerIntervalGroup table, the GroupIdx index is reset not to allow duplicate records.

  


