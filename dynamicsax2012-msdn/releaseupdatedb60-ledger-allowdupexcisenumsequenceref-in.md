---
title: ReleaseUpdateDB60_Ledger.allowDupExciseNumSequenceRef_IN
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupExciseNumSequenceRef_IN
ms:assetid: fcedeea0-4941-50e6-63f7-28a9154fc7a2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720156(v=AX.60)
ms:contentKeyID: 49712461
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupExciseNumSequenceRef\_IN 


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
<td><p>allowDupExciseNumSequenceRef_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ExciseNumRefIdx index in the ExciseNumSequenceRef_IN table to allow for duplicate records.</p></td>
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
<td><p>ExciseNumSequenceRef_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The RegistrationNumber field is replaced with the new Reference and TaxRegistrationNumberTable surrogate key fields in the ExciseNumRefIdx unique index. Initially the TaxRegistrationNumberTable field contains no value. So the index is set to allow for duplicates before the field is updated with the value of the RecId fields in the TaxRegistrationNumberTable\_IN table.

  


