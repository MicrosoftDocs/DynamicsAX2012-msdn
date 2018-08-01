---
title: ReleaseUpdateDB60_Proj.updateProjForecastEmpl Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateProjForecastEmpl Upgrade Script
ms:assetid: 0421c954-97ef-3355-6fe2-dc2a7f36e42f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684681(v=AX.60)
ms:contentKeyID: 49706376
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateProjForecastEmpl Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Proj</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateProjForecastEmpl</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates activity, resource requirement, and capability requirement for existing hour forecast records.</p></td>
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
<td><p>Project</p></td>
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
<td><p>WrkCtrActivity</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrProjForecastEmplActivity</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrActivityRequirement</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrActivityRequirementSet</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrActivityResourceRequirement</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrActivityResourceGroupRequirement</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrActivityCapabilityRequirement</p></td>
</tr>
</tbody>
</table>


## Remarks

Creates WrkCtrActivity, WrkCtrProjForecastEmplActivity, WrkCtrActivityRequirementSet, WrkCtrActivityRequirement, WrkCtrActivityResourceRequirement, WrkCtrActivityResourceGroupRequirement, and WrkCtrActivityCapabilityRequirement records for existing ProjForecastEmpl records.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjForecastEmpl</p></th>
<th><p>To Table: WrkCtrProjForecastEmplActivity</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TransId</p></td>
<td><p>TransId</p></td>
</tr>
<tr class="even">
<td><p>DataAreaId</p></td>
<td><p>ForecastEmplDataAreaId</p></td>
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
<th><p>From Table: ProjForecastEmpl</p></th>
<th><p>To Table: WrkCtrActivityRequirementSet</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_SchedLoadPct</p></td>
<td><p>LoadPercent</p></td>
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
<td><p>ProjForecastEmpl</p></td>
<td><p>DEL_DEL_SchedTaskDemandSchedLoadPct</p></td>
</tr>
<tr class="even">
<td><p>ProjForecastEmpl</p></td>
<td><p>DEL_WrkCtrNum</p></td>
</tr>
<tr class="odd">
<td><p>ProjForecastEmpl</p></td>
<td><p>DEL_SchedTaskGroupId</p></td>
</tr>
<tr class="even">
<td><p>ProjForecastEmpl</p></td>
<td><p>DEL_SchedTaskDemand</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

