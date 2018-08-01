---
title: ReleaseUpdateDB60_HRM.updateHcmWorkerAffiliationAdvHolder_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmWorkerAffiliationAdvHolder_RU Upgrade Script
ms:assetid: cffa06b8-4066-826a-1b07-9a089fc20149
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686916(v=AX.60)
ms:contentKeyID: 49711366
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmWorkerAffiliationAdvHolder\_RU Upgrade Script 


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
<td><p>updateHcmWorkerAffiliationAdvHolder_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmWorkerAffiliationAdvHolder_RU table from the EmplTable table.</p></td>
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
<td><p>HcmWorkerAffiliationAdvHolder_RU</p></td>
</tr>
</tbody>
</table>


## Remarks

The WorkerAffiliation field in the HcmWorkerAffiliationAdvHolder\_RU table is the foreign key for the HcmWorkerAffiliation table. The WorkerGroup field in the HcmWorkerAffiliationAdvHolder\_RU table is the foreign key for the HcmWorkerGroup\_RU table. The IdentityCard field in the HcmWorkerAffiliationAdvHolder\_RU table is the foreign key for the HcmIdentityCardTable\_RU table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMPartyEmployeeRelationship</p></th>
<th><p>To Table: HcmWorkerAffiliationAdvHolder_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ValidFromDateTime</p></td>
<td><p>ValidFrom</p></td>
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
<th><p>From Table: HcmIdentityCardTable_RU</p></th>
<th><p>To Table: HcmWorkerAffiliationAdvHolder_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>IdentityCard</p></td>
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
<th><p>From Table: EmplTable</p></th>
<th><p>To Table: HcmWorkerAffiliationAdvHolder_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IdentityCardNumber_RU</p></td>
<td><p>IdentityCardNumber</p></td>
</tr>
<tr class="even">
<td><p>IdentityCardIssueBy_RU</p></td>
<td><p>IdentityCardIssueBy</p></td>
</tr>
<tr class="odd">
<td><p>IdentityCardIssueDate_RU</p></td>
<td><p>IdentityCardIssueDate</p></td>
</tr>
<tr class="even">
<td><p>IdentityCardSeries_RU</p></td>
<td><p>IdentityCardSeries</p></td>
</tr>
<tr class="odd">
<td><p>AdvHolder_RU</p></td>
<td><p>AdvHolder</p></td>
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
<th><p>From Table: HcmWorkerGroup_RU</p></th>
<th><p>To Table: HcmWorkerAffiliationAdvHolder_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>WorkerGroup</p></td>
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
<th><p>From Table: HcmWorkerAffiliation</p></th>
<th><p>To Table: HcmWorkerAffiliationAdvHolder_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>WorkerAffiliation</p></td>
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
<td><p>HcmWorkerAffiliationAdvHolder_RU</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


