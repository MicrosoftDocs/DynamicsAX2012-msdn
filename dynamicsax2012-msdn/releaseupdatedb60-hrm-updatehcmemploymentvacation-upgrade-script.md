---
title: ReleaseUpdateDB60_HRM.updateHcmEmploymentVacation Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmEmploymentVacation Upgrade Script
ms:assetid: 9a7a2bc1-5c49-e85a-ad19-a97c9640c1dd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686299(v=AX.60)
ms:contentKeyID: 49710003
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmEmploymentVacation Upgrade Script 


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
<td><p>updateHcmEmploymentVacation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmEmploymentVacation table from the DEL_HRMPartyEmployeeRelationship table.</p></td>
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
<td><p>HcmEmploymentVacation</p></td>
</tr>
</tbody>
</table>


## Remarks

The Employment field in the HcmEmploymentVacation table is the foreign key to the HcmEmployment table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_HRMPartyEmployeeRelationship</p></th>
<th><p>To Table: HcmEmploymentVacation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ValidFromDateTime</p></td>
<td><p>ValidFrom</p></td>
</tr>
<tr class="even">
<td><p>ValidToDateTime</p></td>
<td><p>ValidTo</p></td>
</tr>
<tr class="odd">
<td><p>Holidays</p></td>
<td><p>HolidaysPerYear</p></td>
</tr>
<tr class="even">
<td><p>TotalVacationHours</p></td>
<td><p>VacationHoursTotal</p></td>
</tr>
<tr class="odd">
<td><p>VacationHoursTaken</p></td>
<td><p>VacationHoursTaken</p></td>
</tr>
<tr class="even">
<td><p>VacationHoursLeft</p></td>
<td><p>VacationHoursLeft</p></td>
</tr>
<tr class="odd">
<td><p>VacationHoursCarriedOver</p></td>
<td><p>VacationHoursCarriedOver</p></td>
</tr>
<tr class="even">
<td><p>VacationPayment</p></td>
<td><p>VacationPay</p></td>
</tr>
<tr class="odd">
<td><p>VacationWithSalary</p></td>
<td><p>IsPaidVacation</p></td>
</tr>
<tr class="even">
<td><p>CareWithSalary</p></td>
<td><p>IsPaidPersonalDays</p></td>
</tr>
<tr class="odd">
<td><p>DaysOffWithSalary</p></td>
<td><p>IsPaidHolidays</p></td>
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
<th><p>To Table: HcmEmploymentVacation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>Employment</p></td>
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
<td><p>HcmEmploymentVacation</p></td>
<td><p>*</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

