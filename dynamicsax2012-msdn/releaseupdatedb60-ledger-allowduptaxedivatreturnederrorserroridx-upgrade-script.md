﻿---
title: ReleaseUpdateDB60_Ledger.allowDupTaxEdivatReturnedErrorsErrorIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxEdivatReturnedErrorsErrorIdx Upgrade Script
ms:assetid: b7a2a752-a4a4-d670-8ea2-a16b57242115
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737064(v=AX.60)
ms:contentKeyID: 49710746
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxEdivatReturnedErrorsErrorIdx Upgrade Script 


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
<td><p>allowDupTaxEdivatReturnedErrorsErrorIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ErrorIdx index in the TaxEdivatReturnedErrors table to allow for duplicate records.</p></td>
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
<td><p>TaxEdivatReturnedErrors</p></td>
</tr>
</tbody>
</table>


## Remarks

The TaxEdivatId and TaxEdivatErrorCode fields are replaced with the new TaxEdivatGeneral and TaxEdivatErrors surrogate key fields, respectively, in the unique ErrorIdx index. Initially, these fields contain no value. Therefore, the index is set to allow for duplicate values before the fields are updated with the value of the RecId field of the TaxEdivatGeneral and TaxEdivatErrors tables, respectively.

  


