---
title: ReleaseUpdateDB60_Ledger.allowNoDupNumberPeriod_CNNumSeqPeriodIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupNumberPeriod_CNNumSeqPeriodIdx Upgrade Script
ms:assetid: 1a50f491-a6c8-e0e7-0447-46207398e83f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718648(v=AX.60)
ms:contentKeyID: 49706928
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupNumberPeriod\_CNNumSeqPeriodIdx Upgrade Script 


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
<td><p>allowNoDupNumberPeriod_CNNumSeqPeriodIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;NumSeqPeriodIdx&lt;/c&gt; in the table &lt;c&gt;NumberPeriod_CN&lt;/c&gt; not to allow duplicate records.</p></td>
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

After updating the surrogate key field NumberPeriod\_CN with the value of the RecId field of the table NumberPeriod\_CN, the index NumSeqPeriodIdx is reset not to allow duplicate records.

  


