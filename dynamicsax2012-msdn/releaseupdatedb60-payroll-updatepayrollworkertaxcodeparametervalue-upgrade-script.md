---
title: ReleaseUpdateDB60_Payroll.updatePayrollWorkerTaxCodeParameterValue Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollWorkerTaxCodeParameterValue Upgrade Script
ms:assetid: 9225d46d-26e7-07e6-c88e-f726676b8b02
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736599(v=AX.60)
ms:contentKeyID: 49709787
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollWorkerTaxCodeParameterValue Upgrade Script 


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
<td><p>updatePayrollWorkerTaxCodeParameterValue</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates records in the PayrollWorkerTaxCodeParameterValue table by using values from the following tables: PrlEmployeeUSFederalTaxSetup, PrlEmployeeUSStateTaxSetup, and PrlEmployeeUSLocalTaxSetup.</p></td>
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
<td><p>PAYROLLWORKERTAXCODEPARAMETERVALUE</p></td>
</tr>
<tr class="even">
<td><p>PAYROLLWORKERTAXCODE</p></td>
</tr>
<tr class="odd">
<td><p>PAYROLLTAXCODE</p></td>
</tr>
<tr class="even">
<td><p>PAYROLLTAXCODEPARAMETER</p></td>
</tr>
<tr class="odd">
<td><p>PAYROLLTAXENGINETAXCODE</p></td>
</tr>
<tr class="even">
<td><p>PRLEMPLOYEEUSFEDERALTAXSETUP</p></td>
</tr>
<tr class="odd">
<td><p>PRLEMPLOYEEUSSTATETAXSETUP</p></td>
</tr>
<tr class="even">
<td><p>PRLEMPLOYEEUSLOCALTAXSETUP</p></td>
</tr>
<tr class="odd">
<td><p>LOGISTICSADDRESSCOUNTRYREGION</p></td>
</tr>
<tr class="even">
<td><p>PRLLOCALWITHHOLDING</p></td>
</tr>
</tbody>
</table>


## Remarks

The PrlEmployeeUSFederalTaxSetup table contains all the federal tax setup information. The PrlEmployeeUSStateTaxSetup table contains all the state tax setup information. The PrlEmployeeUSLocalTaxSetup table contains all the local tax setup information.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PrlEmployeeUSFederalTaxSetup</p></th>
<th><p>To Table: PayrollWorkerTaxCodeParameterValue</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SUTAExemptStatusER</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>FicaExemptStatusER</p></td>
<td><p>Value</p></td>
</tr>
<tr class="odd">
<td><p>FUTAExemptStatusER</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>FicaExemptStatus</p></td>
<td><p>Value</p></td>
</tr>
<tr class="odd">
<td><p>ExptFedWH</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>MedicareExemptStatus</p></td>
<td><p>Value</p></td>
</tr>
<tr class="odd">
<td><p>IsStatutoryEmployee</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>HasRetirementPlan</p></td>
<td><p>Value</p></td>
</tr>
<tr class="odd">
<td><p>HasThirdPartySick</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>SUTAState</p></td>
<td><p>Value</p></td>
</tr>
<tr class="odd">
<td><p>AdditionalFedWithholding</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>FederalFilingStatus</p></td>
<td><p>Value</p></td>
</tr>
<tr class="odd">
<td><p>NumExempt</p></td>
<td><p>Value</p></td>
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
<th><p>From Table: PrlEmployeeUSStateTaxSetup</p></th>
<th><p>To Table: PayrollWorkerTaxCodeParameterValue</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>StateExempt</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>AdditionalStateWithholding</p></td>
<td><p>Value</p></td>
</tr>
<tr class="odd">
<td><p>NonResidentCertificate</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>SupplementalCalculationMethod</p></td>
<td><p>Value</p></td>
</tr>
<tr class="odd">
<td><p>MiscellaneousValues</p></td>
<td><p>Value</p></td>
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
<th><p>From Table: PrlEmployeeUSLocalTaxSetup</p></th>
<th><p>To Table: PayrollWorkerTaxCodeParameterValue</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CityExemptions</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>MiscellaneousValues</p></td>
<td><p>Value</p></td>
</tr>
</tbody>
</table>

  


