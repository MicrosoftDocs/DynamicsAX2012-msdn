---
title: ReleaseUpdateDB60_Ledger.allowDupNumberPeriod_CNNumSeqPeriodIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupNumberPeriod_CNNumSeqPeriodIdx Upgrade Script
ms:assetid: c4542a02-b2d7-794f-8ffc-eaec38ee9e24
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686865(v=AX.60)
ms:contentKeyID: 49711062
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupNumberPeriod\_CNNumSeqPeriodIdx Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>allowDupNumberPeriod_CNNumSeqPeriodIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the NumSeqPeriodIdx index in the NumberPeriod_CN table to allow duplicate records.</p></td>
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
<td><p>NUMBERPERIOD_CN</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the NumSeqPeriodIdx index of the NumberPeriod\_CN surrogate key field with the value of the RecId field of the NumberPeriod\_CN table to allow duplicate.

  


