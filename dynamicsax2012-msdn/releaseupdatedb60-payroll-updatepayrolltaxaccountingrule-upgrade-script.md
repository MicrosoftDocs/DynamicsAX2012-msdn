---
title: ReleaseUpdateDB60_Payroll.updatePayrollTaxAccountingRule Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollTaxAccountingRule Upgrade Script
ms:assetid: 8ff7c3cd-744c-9469-1104-239d0fe8093f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736553(v=AX.60)
ms:contentKeyID: 49709743
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollTaxAccountingRule Upgrade Script 


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
<td><p>updatePayrollTaxAccountingRule</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;PayrollTaxAccountingRule&lt;/c&gt; table from the &lt;c&gt;PRLPostingSetupDetails&lt;/c&gt; table.</p></td>
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
<td><p>PAYROLLTAXACCOUNTINGRULE</p></td>
</tr>
<tr class="even">
<td><p>PAYROLLTAXCODE</p></td>
</tr>
<tr class="odd">
<td><p>LOGISTICSADDRESSCOUNTRYREGION</p></td>
</tr>
<tr class="even">
<td><p>PRLPOSTINGSETUPDETAILS</p></td>
</tr>
</tbody>
</table>


## Remarks

Only records in the \<c\>PRLPostingSetupDetails\</c\> table with the field \<c\>BranchCode\</c\> set to \<c\>All\</c\> and the field \<c\>EmplCode\</c\> set to \<c\>All\</c\> will get records created in the \<c\>PayrollTaxAccountingRule\</c\> table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PRLPostingSetupDetails</p></th>
<th><p>To Table: PayrollTaxAccountingRule</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PayElementCode</p></td>
<td><p>PayrollTaxCode</p></td>
</tr>
<tr class="even">
<td><p>dataAreaId</p></td>
<td><p>LegalEntity</p></td>
</tr>
<tr class="odd">
<td><p>AccountNum, AccountType</p></td>
<td><p>LedgerDimension</p></td>
</tr>
</tbody>
</table>

  


