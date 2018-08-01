---
title: ReleaseUpdateDB60_Payroll.updatePayrollEarningCode Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollEarningCode Upgrade Script
ms:assetid: ab44115e-bcf8-718e-34b4-a996bfa5267b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686470(v=AX.60)
ms:contentKeyID: 49710426
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollEarningCode Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>updatePayrollEarningCode</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the PayrollEarningCode, PayrollEarningCodeDetail, PayrollEarningExternalReporting_US, PayrollGrossUpEarningCodeReference, and PayrollEarningCodeAccountingRule tables.</p></td>
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
<td><p>PayrollEarningCode</p></td>
</tr>
<tr class="even">
<td><p>PayrollEarningCodeDetail</p></td>
</tr>
<tr class="odd">
<td><p>PayrollEarningCodeExternalReporting_US</p></td>
</tr>
<tr class="even">
<td><p>PayrollEarningCodeAccountingRule</p></td>
</tr>
</tbody>
</table>


## Remarks

The records in the PRLPayElements table with the PRLPayElementType::Earning value in the PaymentType field need to be upgraded into the PayrollEarningCode table and the PayrollEarningCodeDetail table. The W2 related BoxLetter and BoxNumber fields are upgraded to the PayrollEarningExternalReporting\_US table. For gross earning code, a record in the PayrollGrossUpEarningCodeReference table should be created to reflect the relationship between the gross up earning code and the secondary earning code. Creates records in the PayrollEarningCodeAccountingRule table from the PRLPostingSetupDetails table for the PRLPayElement table records with earning type.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PRLPayElement</p></th>
<th><p>To Table: PayrollEarningCode</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PayElementCode</p></td>
<td><p>EarningCode</p></td>
</tr>
<tr class="even">
<td><p>PayElementGroup</p></td>
<td><p>EarningCode</p></td>
</tr>
<tr class="odd">
<td><p>Description</p></td>
<td><p>Description</p></td>
</tr>
<tr class="even">
<td><p>Imputed</p></td>
<td><p>FringeBenefitType</p></td>
</tr>
<tr class="odd">
<td><p>PRL_GTL</p></td>
<td><p>FringeBenefitType</p></td>
</tr>
<tr class="even">
<td><p>PrimaryCode</p></td>
<td><p>IsBaseSalaryComponent</p></td>
</tr>
<tr class="odd">
<td><p>CalcOfSal</p></td>
<td><p>QuantityUnit</p></td>
</tr>
<tr class="even">
<td><p>IncludeInRegular</p></td>
<td><p>IncludeInPaymentType</p></td>
</tr>
<tr class="odd">
<td><p>Taxable</p></td>
<td><p>TaxMethod</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PRLPayElement</p></th>
<th><p>To Table: PayrollEarningCodeDetail</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PayElementCode</p></td>
<td><p>EarningCode</p></td>
</tr>
<tr class="even">
<td><p>PayElementGroup</p></td>
<td><p>EarningCode</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PRLPayElement</p></th>
<th><p>To Table: PayrollGrossUpEarningCodeReference</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>GrossUpEarningCode</p></td>
<td><p>GrossUpEarningCode</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PRLPayElement</p></th>
<th><p>To Table: PayrollEarningCodeExternalReporting_US</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>BoxNumber</p></td>
<td><p>W2BoxNumber</p></td>
</tr>
<tr class="even">
<td><p>BoxLabel</p></td>
<td><p>W2BoxLabel</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PRLPostingSetupDetails</p></th>
<th><p>To Table: PayrollEarningCodeAccountingRule</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DataAreaID</p></td>
<td><p>LegalEntity</p></td>
</tr>
<tr class="even">
<td><p>AccountNum</p></td>
<td><p>LedgerDimension</p></td>
</tr>
</tbody>
</table>


## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PayrollEarningCode</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>PayrollEarningCodeDetail</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>PayrollGrossUpEarningCodeReference</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>PayrollEarningCodeExternalReporting_US</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>PayrollEarningCodeAccountingRule</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


