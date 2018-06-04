---
title: ReleaseUpdateDB60_Proj.updateDataAreaAndLegalEntityFields Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateDataAreaAndLegalEntityFields Upgrade Script
ms:assetid: 5330610e-35c2-7187-8588-507918101c98
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685574(v=AX.60)
ms:contentKeyID: 49708266
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateDataAreaAndLegalEntityFields Upgrade Script 


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
<td><p>updateDataAreaAndLegalEntityFields</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Enters information in the ProjectDataArea and WorkerLegalEntity fields for the intercompany timesheets feature.</p></td>
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
<td><p>TSTimesheetLine</p></td>
</tr>
<tr class="even">
<td><p>TSTimesheetFavorites</p></td>
</tr>
<tr class="odd">
<td><p>ProjValEmplProjSetup</p></td>
</tr>
<tr class="even">
<td><p>ProjValEmplCategorySetUp</p></td>
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
<td><p>TSTimesheetLine</p></td>
<td><p>ProjectDataAreaId</p></td>
<td><p>dataAreaId</p></td>
</tr>
<tr class="even">
<td><p>TSTimesheetFavorites</p></td>
<td><p>ProjectDataAreaId</p></td>
<td><p>dataAreaId</p></td>
</tr>
<tr class="odd">
<td><p>ProjValEmplProjSetup</p></td>
<td><p>WorkerLegalEntity</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>ProjValEmplCategorySetup</p></td>
<td><p>WorkerLegalEntity</p></td>
<td><p>RefRecId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

