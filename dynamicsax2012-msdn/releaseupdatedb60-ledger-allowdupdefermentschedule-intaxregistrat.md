---
title: ReleaseUpdateDB60_Ledger.allowDupDefermentSchedule_INTaxRegistrat
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupDefermentSchedule_INTaxRegistrat
ms:assetid: 95bfb4ee-966c-7f64-d33c-281fd832a184
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686165(v=AX.60)
ms:contentKeyID: 49709869
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupDefermentSchedule\_INTaxRegistrat 


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
<td><p>allowDupDefermentSchedule_INTaxRegistrat</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;TaxRegistrationNumberIdx&lt;/c&gt; in the table &lt;c&gt;DefermentSchedule_IN&lt;/c&gt; to allow duplicate records.</p></td>
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
<td><p>DEFERMENTSCHEDULE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The RegistrationNumber field is replaced with the new surrogate key field Reference and TaxRegistrationNumberTable in the unique index TaxRegistrationNumberTableIdx. Initially the TaxRegistrationNumberTable field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields of the table TaxRegistrationNumberTable\_IN.

  


