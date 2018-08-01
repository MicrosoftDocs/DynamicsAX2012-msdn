---
title: ReleaseUpdateDB60_Payroll.updatePrlUSTaxTransactionHistory Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePrlUSTaxTransactionHistory Upgrade Script
ms:assetid: 4cacaf3b-64dd-79ce-022e-2582617a9faf
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685421(v=AX.60)
ms:contentKeyID: 49708126
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePrlUSTaxTransactionHistory Upgrade Script 


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
<td><p>updatePrlUSTaxTransactionHistory</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates records in the PrlUSTaxTransactionHistory table replacing the following relationships PRLEmployeePayElementsTransPosted table with a relationship to the PayrollPayStatement and DEL_EmplTable table with a relationship to the HcmWorker table.</p></td>
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
<td><p>PrlUSTaxTransactionHistory</p></td>
</tr>
<tr class="even">
<td><p>PRLEmployeePayElementsTransPosted</p></td>
</tr>
<tr class="odd">
<td><p>DEL_EmplTable</p></td>
</tr>
<tr class="even">
<td><p>PayrollTaxEngineTaxCodeForSymmetry</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsAddressCountryRegion</p></td>
</tr>
<tr class="even">
<td><p>HcmWorker</p></td>
</tr>
</tbody>
</table>


## Remarks

Replaces the following fields of the PrlUSTaxTransactionHistory table: The PayStatement field with the corresponding value from the DEL\_MappingRecId field of the PRLEmployeePayElementsTransPosted table, The DEL\_EmplId field with the corresponding value from the record ID of the HcmWorker table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HcmWorker</p></th>
<th><p>To Table: PrlUSTaxTransactionHistory</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>Worker</p></td>
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
<th><p>From Table: PRLEmployeePayElementsTransPosted</p></th>
<th><p>To Table: PrlUSTaxTransactionHistory</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_MappingRec</p></td>
<td><p>PayStatement</p></td>
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
<th><p>From Table: PayrollTaxEngineTaxCodeForSymmetry</p></th>
<th><p>To Table: PrlUSTaxTransactionHistory</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PayrollTaxCode</p></td>
<td><p>TaxCode</p></td>
</tr>
</tbody>
</table>

  


