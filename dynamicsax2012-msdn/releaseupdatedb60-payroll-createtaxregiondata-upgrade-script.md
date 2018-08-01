---
title: ReleaseUpdateDB60_Payroll.createTaxRegionData Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.createTaxRegionData Upgrade Script
ms:assetid: 2d8a286c-3140-d680-5a09-417341992e68
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735996(v=AX.60)
ms:contentKeyID: 49707413
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.createTaxRegionData Upgrade Script 


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
<td><p>createTaxRegionData</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the following tables: PayrollTaxRegion, PayrollTaxRegionForSymmetry, LogisticsLocation, LogisticsPostalAddress, PayrollWorkerTaxRegion, PayrollWorkerTaxRegionForSymmetry, PayrollWorkerResidentTaxRegion, and PayrollPositionWorkerDefaultTaxRgn.</p></td>
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
<td><p>PayrollTaxRegion</p></td>
</tr>
<tr class="even">
<td><p>PayrollTaxRegionForSymmetry</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsLocation</p></td>
</tr>
<tr class="even">
<td><p>LogisiticsPostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>PayrollWorkerTaxRegion</p></td>
</tr>
<tr class="even">
<td><p>PayrollWorkerTaxRegionForSymmetry</p></td>
</tr>
<tr class="odd">
<td><p>PayrollWorkerResidentTaxRegion</p></td>
</tr>
<tr class="even">
<td><p>PayrollPositionWorkerDefaultTaxRgn</p></td>
</tr>
<tr class="odd">
<td><p>PrePRLEMPLOYEEUSLOCALTAXSETUP</p></td>
</tr>
<tr class="even">
<td><p>LogisticsAddressCountryRegion</p></td>
</tr>
<tr class="odd">
<td><p>PayrollTaxCodeParameter</p></td>
</tr>
<tr class="even">
<td><p>PayrollTaxCodeParameterDetail</p></td>
</tr>
<tr class="odd">
<td><p>PayrollTaxEngineTaxCodeForSymmetry</p></td>
</tr>
<tr class="even">
<td><p>PayrollWorkerTaxCode</p></td>
</tr>
<tr class="odd">
<td><p>PayrollWorkerTaxCodeParameterValue</p></td>
</tr>
<tr class="even">
<td><p>PayrollPositionDetail</p></td>
</tr>
<tr class="odd">
<td><p>HCMPositionWorkerAssignment</p></td>
</tr>
</tbody>
</table>


## Remarks

For every distinct GNISLocation record in the PRLEmployeeUSLocalTaxSetup table, a new record will be inserted into the following tables: PayrollTaxRegion, PayrollTaxRegionForSymmetry, LogisticsLocation, and LogisticsPostalAddress. For a specified GNISLocation record, the following tables will have new records inserted based on the number of records in the PRLEmployeeUSLocalTaxSetup table: PayrollWorkerTaxRegion, PayrollWorkerTaxRegionForSymmetry, PayrollWorkerResidentTaxRegion. Finally, all PRLEmployeeUSLocalTaxSetup records with the EntryDefault field set to Yes will create a new record in the PayrollPositionWorkerDefaultTaxRgn table for every HcmPositionWorkerAssignment record that is assigned to the specified worker.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PrlEmployeeUSLocalTaxSetup</p></th>
<th><p>To Table: LogisticsLocation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>State, County, City</p></td>
<td><p>Description</p></td>
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
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>City</p></td>
<td><p>City</p></td>
</tr>
<tr class="even">
<td><p>County</p></td>
<td><p>County</p></td>
</tr>
<tr class="odd">
<td><p>State</p></td>
<td><p>State</p></td>
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
<th><p>To Table: PayrollTaxRegionForSymmetry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>GNISLocation</p></td>
<td><p>GNIS</p></td>
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
<th><p>To Table: PayrollWorkerTaxRegion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EmplId</p></td>
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
<th><p>From Table: PrlEmployeeUSLocalTaxSetup</p></th>
<th><p>To Table: PayrollWorkerTaxRegionForSymmetry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SchoolId</p></td>
<td><p>SchoolDistrictId</p></td>
</tr>
<tr class="even">
<td><p>MunFeatureId</p></td>
<td><p>MunicipalityId</p></td>
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
<th><p>To Table: PayrollWorkerResidentTaxRegion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EmplId</p></td>
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
<th><p>From Table: PrlEmployeeUSLocalTaxSetup</p></th>
<th><p>To Table: PayrollPositionWorkerDefaultTaxRegion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Emplid</p></td>
<td><p>Worker</p></td>
</tr>
</tbody>
</table>

  


