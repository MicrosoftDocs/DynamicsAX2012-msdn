---
title: ReleaseUpdateDB60_smm.updatesmmOpportunityTableWorker Upgrade Script
TOCTitle: ReleaseUpdateDB60_smm.updatesmmOpportunityTableWorker Upgrade Script
ms:assetid: 0f595264-ac58-c825-34a1-041d1d641af3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735757(v=AX.60)
ms:contentKeyID: 49706670
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_smm.updatesmmOpportunityTableWorker Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_smm</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatesmmOpportunityTableWorker</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates data from the DEL_OwnerId field to the OwnerWorker field, the DEL_OpenedBy field to the OpenedByWorker field, and the DEL_ClosedBy field to the ClosedByWorker field in the smmOpportunityTable table.</p></td>
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
<td><p>CRM</p></td>
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
<td><p>smmOpportunityTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The HCMWorker table and associated tables have replaced the Employee table, that is the EmplTable table, and associated tables in Microsoft Dynamics AX 2012. This transition requires an upgrade.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: smmOpportunityTable</p></th>
<th><p>To Table: smmOpportunityTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_OwnerId</p></td>
<td><p>OwnerWorker</p></td>
</tr>
<tr class="even">
<td><p>DEL_OpenedBy</p></td>
<td><p>OpenedByWorker</p></td>
</tr>
<tr class="odd">
<td><p>DEL_ClosedBy</p></td>
<td><p>ClosedByWorker</p></td>
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
<td><p>smmOpportunityTable</p></td>
<td><p>OwnerWorker</p></td>
<td><p>CrmWorkerRecId</p></td>
</tr>
<tr class="even">
<td><p>smmOpportunityTable</p></td>
<td><p>OpenedByWorker</p></td>
<td><p>CrmWorkerRecId</p></td>
</tr>
<tr class="odd">
<td><p>smmOpportunityTable</p></td>
<td><p>ClosedByWorker</p></td>
<td><p>CrmWorkerRecId</p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>smmOpportunityTable</p></td>
<td><p>DEL_OwnerId</p></td>
</tr>
<tr class="even">
<td><p>smmOpportunityTable</p></td>
<td><p>DEL_OpenedBy</p></td>
</tr>
<tr class="odd">
<td><p>smmOpportunityTable</p></td>
<td><p>DEL_ClosedBy</p></td>
</tr>
</tbody>
</table>

  


