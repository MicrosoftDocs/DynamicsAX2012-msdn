---
title: ReleaseUpdateDB60_Payroll.updatePrlDeductionArrearRecovery Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePrlDeductionArrearRecovery Upgrade Script
ms:assetid: b7895dcd-aca1-5e32-e01d-3946ef65c453
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737047(v=AX.60)
ms:contentKeyID: 49710729
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePrlDeductionArrearRecovery Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Payroll</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePrlDeductionArrearRecovery</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates records in the PRLDeductionArrearRecovery table.</p></td>
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
<td><p>Payroll</p></td>
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
<td><p>PRLDeductionArrearRecovery</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the AccountingCurrencyAmount and DeductionArrear fields of the PRLDeductionArrearRecovery table from the Amount and ArrearRecId fields.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PrlDeductionArrearRecovery</p></th>
<th><p>To Table: PrlDeductionArrearRecovery</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Amount</p></td>
<td><p>AccountingCurrencyAmount</p></td>
</tr>
<tr class="even">
<td><p>ArrearRecId</p></td>
<td><p>DeductionArrear</p></td>
</tr>
</tbody>
</table>

  


