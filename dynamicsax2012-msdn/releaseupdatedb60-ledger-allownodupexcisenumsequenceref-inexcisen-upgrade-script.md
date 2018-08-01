---
title: ReleaseUpdateDB60_Ledger.allowNoDupExciseNumSequenceRef_INExciseN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupExciseNumSequenceRef_INExciseN Upgrade Script
ms:assetid: 1993acb3-4165-1eac-4663-9815e42af9cb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718634(v=AX.60)
ms:contentKeyID: 49706933
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupExciseNumSequenceRef\_INExciseN Upgrade Script 


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
<td><p>Updates the ExciseNumRefIdx index in the ExciseNumSequenceRef_IN table to not allow duplicate records.</p></td>
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

After updating the TaxRegistrationNumberTable surrogate key fields with the value of the RecId field of the tables, the ExciseNumRefIdx index is reset not to allow duplicate records.

  


