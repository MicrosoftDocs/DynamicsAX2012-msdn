---
title: ReleaseUpdateDB60_Ledger.allowDupNumberPeriod_CNNumSeqPeriodIdx
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupNumberPeriod_CNNumSeqPeriodIdx
ms:assetid: 32fcdf95-581a-1f9c-eea4-3797e73d7622
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685087(v=AX.60)
ms:contentKeyID: 49707541
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupNumberPeriod\_CNNumSeqPeriodIdx [AX 2012]


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
<td><p>Updates the index &lt;c&gt;NumSeqPeriodIdx&lt;/c&gt; in the table &lt;c&gt;NumberPeriod_CN&lt;/c&gt; to allow duplicate records.</p></td>
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

Updates the index NumSeqPeriodIdx of the surrogate key field NumberPeriod\_CN with the value of the RecId field of the table NumberPeriod\_CN to allow duplicate.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

