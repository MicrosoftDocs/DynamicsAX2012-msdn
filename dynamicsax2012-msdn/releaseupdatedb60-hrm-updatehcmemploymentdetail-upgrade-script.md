---
title: ReleaseUpdateDB60_HRM.updateHcmEmploymentDetail Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmEmploymentDetail Upgrade Script
ms:assetid: e98685ea-b105-9a80-76ee-4266d7425151
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719866(v=AX.60)
ms:contentKeyID: 49711940
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmEmploymentDetail Upgrade Script 


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
<td><p>updateHcmEmploymentDetail</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmEmploymentDetail table from the HRMPartyEmployeeRelationship table.</p></td>
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
<td><p>HcmEmploymentDetail</p></td>
</tr>
</tbody>
</table>


## Remarks

The Employment field in the HcmEmploymentDetail table is the foreign key to the HcmEmployment table. The TransitionReasonCode field in the HcmEmploymentDetail table is the foreign key to the HcmReasonCode table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMPartyEmployeeRelationship</p></th>
<th><p>To Table: HcmEmploymentDetail</p></th>
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
<td><p>EmployerTerminationNoticeUnit</p></td>
<td><p>EmployerUnitOfNotice</p></td>
</tr>
<tr class="even">
<td><p>EmployerTerminationNotice</p></td>
<td><p>EmployerNoticeAmount</p></td>
</tr>
<tr class="odd">
<td><p>EmployeeTerminationNoticeUnit</p></td>
<td><p>WorkerUnitOfNotice</p></td>
</tr>
<tr class="even">
<td><p>EmployeeTerminationNotice</p></td>
<td><p>WorkerNoticeAmount</p></td>
</tr>
<tr class="odd">
<td><p>StartDate</p></td>
<td><p>WorkerStartDate</p></td>
</tr>
<tr class="even">
<td><p>AdjustedStartDate</p></td>
<td><p>AdjustedWorkerStartDate</p></td>
</tr>
<tr class="odd">
<td><p>LastDateWorked</p></td>
<td><p>LastDateWorked</p></td>
</tr>
<tr class="even">
<td><p>TerminationDate</p></td>
<td><p>TransitionDate</p></td>
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
<th><p>To Table: HcmEmploymentDetail</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Recid</p></td>
<td><p>Employment</p></td>
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
<th><p>From Table: DEL_HRMReasonCode</p></th>
<th><p>To Table: HcmEmploymentDetail</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_MappingRecId</p></td>
<td><p>TransitionReasonCode</p></td>
</tr>
</tbody>
</table>

  


