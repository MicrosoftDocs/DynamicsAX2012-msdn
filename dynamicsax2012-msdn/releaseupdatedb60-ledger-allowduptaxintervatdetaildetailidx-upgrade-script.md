---
title: ReleaseUpdateDB60_Ledger.allowDupTaxIntervatDetailDetailIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxIntervatDetailDetailIdx Upgrade Script
ms:assetid: 339f1c4d-eb72-aa91-4c38-78f06711464f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685109(v=AX.60)
ms:contentKeyID: 49707563
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxIntervatDetailDetailIdx Upgrade Script 


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
<td><p>allowDupTaxIntervatDetailDetailIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the DetailIdx index in the TaxIntervatDetail table to allow for duplicate records.</p></td>
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
<td><p>TaxIntervatDetail</p></td>
</tr>
</tbody>
</table>


## Remarks

The TaxIntervatId field is replaced with the new TaxIntervatGeneral surrogate key field in the unique DetailIdx index. Initially, this field contains no value. Therefore, the index is set to allow for duplicate values before the field is updated with the value of the RecId field of the TaxIntervatGeneral table.

  


