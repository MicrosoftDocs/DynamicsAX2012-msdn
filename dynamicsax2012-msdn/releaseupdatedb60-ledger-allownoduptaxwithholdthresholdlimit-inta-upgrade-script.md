---
title: ReleaseUpdateDB60_Ledger.allowNoDupTaxWithholdThresholdLimit_INTa Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupTaxWithholdThresholdLimit_INTa Upgrade Script
ms:assetid: ba91b1ef-d768-d43d-00f4-e660391ec743
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737133(v=AX.60)
ms:contentKeyID: 49710814
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupTaxWithholdThresholdLimit\_INTa Upgrade Script 


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
<td><p>allowNoDupTaxWithholdThresholdLimit_INTa</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TaxWithholdComponentTableIdx index in the TaxWithholdThresholdLimit_IN table to not allow duplicate records.</p></td>
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
<td><p>TAXWITHHOLDTHRESHOLDLIMIT_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the TaxWithholdComponent surrogate key fields with the value of the RecId field of the tables, the TaxWithholdComponentTableIdx index is reset not to allow duplicate records.

  


