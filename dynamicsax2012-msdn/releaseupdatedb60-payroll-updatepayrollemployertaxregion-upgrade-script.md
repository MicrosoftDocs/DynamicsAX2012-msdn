---
title: ReleaseUpdateDB60_Payroll.updatePayrollEmployerTaxRegion Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollEmployerTaxRegion Upgrade Script
ms:assetid: 2a86791d-0bf2-6ac0-04cb-8e9bba53f061
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735928(v=AX.60)
ms:contentKeyID: 49707345
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollEmployerTaxRegion Upgrade Script [AX 2012]


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
<td><p>updatePayrollEmployerTaxRegion</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the PayrollEmployerTaxRegion table from the PRLNexus table.</p></td>
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
<td><p>PAYROLLEMPLOYERTAXREGION</p></td>
</tr>
<tr class="even">
<td><p>PRLNEXUS</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company by assigning the LegalEntity field to the RecId of the CompanyInfo record associated to the old dataAreaId field. In Microsoft Dynamics AX 2009, there were zip code level nexus records. However, this concept was removed for Microsoft Dynamics AX 2012 and only the state level records will be upgraded.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PrlNexus</p></th>
<th><p>To Table: PayrollEmployerTaxRegion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>GNISLocation</p></td>
<td><p>GNIS</p></td>
</tr>
<tr class="even">
<td><p>Country</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>State</p></td>
<td><p>StateId</p></td>
</tr>
<tr class="even">
<td><p>dataAreaId</p></td>
<td><p>LegalEntity</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

