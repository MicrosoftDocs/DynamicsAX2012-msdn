---
title: ReleaseUpdateDB60_Payroll.updatePayrollTaxCodeDetail Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollTaxCodeDetail Upgrade Script
ms:assetid: 717d01f6-0d47-4167-e398-b4c8c95b8b44
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685803(v=AX.60)
ms:contentKeyID: 49709003
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollTaxCodeDetail Upgrade Script [AX 2012]


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
<td><p>updatePayrollTaxCodeDetail</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the PayrollTaxCodeDetail table using values from either the PRLLocalWithholding table or the DEL_AddressState table depending on the type of tax code.</p></td>
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
<td><p>PAYROLLTAXCODEDETAIL</p></td>
</tr>
<tr class="even">
<td><p>PAYROLLTAXCODE</p></td>
</tr>
<tr class="odd">
<td><p>DEL_ADDRESSSTATE</p></td>
</tr>
<tr class="even">
<td><p>LOGISTICSADDRESSCOUNTRYREGION</p></td>
</tr>
<tr class="odd">
<td><p>PRLLOCALWITHHOLDING</p></td>
</tr>
</tbody>
</table>


## Remarks

If the tax code is not an ER\_SUTA value, then the Rate field is set by using the OverrideRate field from the PRLLocalWithholding table. Otherwise, the Rate field is set by using the PRLSUTAExperienceRate field from the DEL\_AddressState table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PRLLocalwithholding</p></th>
<th><p>To Table: PayrollTaxCodeDetail</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>OverrideRate</p></td>
<td><p>Rate</p></td>
</tr>
<tr class="even">
<td><p>dataAreaId</p></td>
<td><p>LegalEntity</p></td>
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
<th><p>From Table: AddressState</p></th>
<th><p>To Table: PayrollTaxCodeDetail</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PRLEmployersStateId</p></td>
<td><p>AccountNumber</p></td>
</tr>
<tr class="even">
<td><p>PRLSUTAExperienceRate</p></td>
<td><p>Rate</p></td>
</tr>
<tr class="odd">
<td><p>dataAreaId</p></td>
<td><p>LegalEntity</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

