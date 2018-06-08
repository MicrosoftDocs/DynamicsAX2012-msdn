---
title: ReleaseUpdateDB60_Ledger.allowDupEximDBKValues_INTariffCodeIdx
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupEximDBKValues_INTariffCodeIdx
ms:assetid: 06a186cd-4dad-4cf7-847a-44fe2312c2af
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684740(v=AX.60)
ms:contentKeyID: 49706435
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupEximDBKValues\_INTariffCodeIdx 


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
<td><p>allowDupEximDBKValues_INTariffCodeIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;TariffCodeIdx&lt;/c&gt; in the table &lt;c&gt;EximDBKValues_IN&lt;/c&gt; to allow duplicate records.</p></td>
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
<td><p>EXIMDBKVALUES_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The TariffCode is replaced with the new surrogate key field CustomsTariffCodeTable in the unique index TariffCodeIdx. Initially the CustomsTariffCodeTable contains no values. So the index is set to allow duplicates before the field is updated with the value of the RecId's of the corresponding tables.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

