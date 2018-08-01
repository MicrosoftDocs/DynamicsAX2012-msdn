---
title: ReleaseUpdateDB60_Ledger.allowDupTaxWithholdReportVoucher_THDateP Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxWithholdReportVoucher_THDateP Upgrade Script
ms:assetid: bb697892-13b6-94be-f181-421467a21ae2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686623(v=AX.60)
ms:contentKeyID: 49710831
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxWithholdReportVoucher\_THDateP Upgrade Script 


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
<td><p>allowDupTaxWithholdReportVoucher_THDateP</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the DatePeriodIdx index in the TaxWithholdReportVoucher_TH table to allow for duplicate records.</p></td>
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
<td><p>TaxWithholdReportVoucher_TH</p></td>
</tr>
</tbody>
</table>


## Remarks

The field TaxWithholdPeriod is replaced with the new TaxWithholdPeriodHead\_TH surrogate key field in the unique DatePeriodIdx index. Initially, this field contains no value. Therefore, the index is set to allow for duplicate values before the field is updated with the value of the RecId field of the TaxWithholdPeriodHead\_TH table.

  


