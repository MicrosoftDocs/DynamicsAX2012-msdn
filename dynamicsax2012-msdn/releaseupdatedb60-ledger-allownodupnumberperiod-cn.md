---
title: ReleaseUpdateDB60_Ledger.allowNoDupNumberPeriod_CN
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupNumberPeriod_CN
ms:assetid: c253c925-c24c-b50e-d18f-44f0b9710854
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686823(v=AX.60)
ms:contentKeyID: 49711019
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupNumberPeriod\_CN 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupNumberPeriod_CN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the NumSeqPeriodIdx index in the NumberPeriod_CN table not to allow for duplicate records.</p></td>
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
<td><p>Ledger</p></td>
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
<td><p>NumberPeriod_CN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the NumberPeriod\_CN surrogate key field with the value of the RecId field of the NumberPeriod\_CN table, the NumSeqPeriodIdx index is reset not to allow for duplicate records.

  


