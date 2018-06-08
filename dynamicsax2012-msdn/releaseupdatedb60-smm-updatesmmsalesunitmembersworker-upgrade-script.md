---
title: ReleaseUpdateDB60_smm.updatesmmSalesUnitMembersWorker Upgrade Script
TOCTitle: ReleaseUpdateDB60_smm.updatesmmSalesUnitMembersWorker Upgrade Script
ms:assetid: 8ed03454-a740-1a1e-c5c6-69caf0d46f9c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736513(v=AX.60)
ms:contentKeyID: 49709702
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_smm.updatesmmSalesUnitMembersWorker Upgrade Script 


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
<td><p>updatesmmSalesUnitMembersWorker</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates data from the DEL_SalesManId field to the SalesManagerWorker field and the DEL_SalesUnitManagerId field to the SalesPersonWorker field in the smmSalesUnitMembers table.</p></td>
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
<td><p>smmSalesUnitMembers</p></td>
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
<th><p>From Table: smmSalesUnitMembers</p></th>
<th><p>To Table: smmSalesUnitMembers</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_SalesManId</p></td>
<td><p>SalesManagerWorker</p></td>
</tr>
<tr class="even">
<td><p>DEL_SalesUnitManagerId</p></td>
<td><p>SalesPersonWorker</p></td>
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
<td><p>smmSalesUnitMembers</p></td>
<td><p>SalesManagerWorker</p></td>
<td><p>CrmWorkerRecId</p></td>
</tr>
<tr class="even">
<td><p>smmSalesUnitMembers</p></td>
<td><p>SalesPersonWorker</p></td>
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
<td><p>smmSalesUnitMembers</p></td>
<td><p>DEL_SalesManId</p></td>
</tr>
<tr class="even">
<td><p>smmSalesUnitMembers</p></td>
<td><p>DEL_SalesUnitManagerId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

