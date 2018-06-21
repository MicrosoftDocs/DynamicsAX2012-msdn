---
title: ReleaseUpdateDB60_HRM.updateHcmEmploymentEmployee Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmEmploymentEmployee Upgrade Script
ms:assetid: e5744ec9-3d38-e966-2105-a405a7513f5c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719781(v=AX.60)
ms:contentKeyID: 49711854
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmEmploymentEmployee Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_HRM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateHcmEmploymentEmployee</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmEmploymentEmployee table from the HRMPartyEmployeeRelationship table.</p></td>
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
<td><p>Human Resources</p></td>
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
<td><p>HcmEmploymentEmployee</p></td>
</tr>
</tbody>
</table>


## Remarks

The Employment field in the HcmEmploymentEmployee table is the foreign key to the HcmEmployment table. The IncomeTaxCategory field in the HcmEmploymentEmployee table is the foreign key to the HcmIncomeTaxCategory table. The IncomeTaxCode field in the HcmEmploymentEmployee table is the foreign key to the HcmIncomeTaxCode table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMPartyEmployeeRelationship</p></th>
<th><p>To Table: HcmEmploymentEmployee</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ValidToDateTime</p></td>
<td><p>ValidTo</p></td>
</tr>
<tr class="even">
<td><p>ValidFromDateTime</p></td>
<td><p>ValidFrom</p></td>
</tr>
<tr class="odd">
<td><p>PayrollCurrency</p></td>
<td><p>Currency</p></td>
</tr>
<tr class="even">
<td><p>PayrollSalaryScaleDate</p></td>
<td><p>SalaryScaleDate</p></td>
</tr>
<tr class="odd">
<td><p>PayrollSalarySeniorityDate</p></td>
<td><p>SalarySeniorityDate</p></td>
</tr>
<tr class="even">
<td><p>PayrollSalaryType</p></td>
<td><p>SalaryType</p></td>
</tr>
<tr class="odd">
<td><p>EmployeeSavingAmount</p></td>
<td><p>EmployeeSavingAmount</p></td>
</tr>
<tr class="even">
<td><p>EmployerSavingAmount</p></td>
<td><p>EmployerSavingAmount</p></td>
</tr>
<tr class="odd">
<td><p>PensionStart</p></td>
<td><p>PensionStartDateEmpl</p></td>
</tr>
<tr class="even">
<td><p>ProbationEndDate</p></td>
<td><p>ProbationDate</p></td>
</tr>
<tr class="odd">
<td><p>PensionEnrollment</p></td>
<td><p>PensionStartDateEmplContract</p></td>
</tr>
<tr class="even">
<td><p>SeniorityDate</p></td>
<td><p>SeniorityDate</p></td>
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
<th><p>From Table: DEL_HRMIncomeTaxCategory</p></th>
<th><p>To Table: HcmEmploymentEmployee</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_MappingRecId</p></td>
<td><p>IncomeTaxCategory</p></td>
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
<th><p>From Table: DEL_HRMIncomeTaxCode</p></th>
<th><p>To Table: HcmEmploymentEmployee</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_MappingRecId</p></td>
<td><p>IncomeTaxCode</p></td>
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
<th><p>From Table: HcmEmployment</p></th>
<th><p>To Table: HcmEmploymentEmployee</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>Employment</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

