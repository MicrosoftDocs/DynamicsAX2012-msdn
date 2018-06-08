---
title: ReleaseUpdateDB60_Ledger.allowNoDupExciseNumSequenceRef_INExciseN
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupExciseNumSequenceRef_INExciseN
ms:assetid: 4843e946-e9f6-2040-514f-6fd5c21db774
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685326(v=AX.60)
ms:contentKeyID: 49708020
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupExciseNumSequenceRef\_INExciseN 


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
<td><p>allowNoDupExciseNumSequenceRef_INExciseN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;ExciseNumRefIdx&lt;/c&gt; in the table &lt;c&gt;ExciseNumSequenceRef_IN&lt;/c&gt; not to allow duplicate records.</p></td>
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
<td><p>EXCISENUMSEQUENCEREF_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the surrogate key fields TaxRegistrationNumberTable with the value of the RecId field of the tables, the index ExciseNumRefIdx is reset not to allow duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

