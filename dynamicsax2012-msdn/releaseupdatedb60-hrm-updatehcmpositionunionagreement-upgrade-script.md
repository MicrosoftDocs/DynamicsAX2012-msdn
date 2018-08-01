---
title: ReleaseUpdateDB60_HRM.updateHcmPositionUnionAgreement Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmPositionUnionAgreement Upgrade Script
ms:assetid: 131dab7d-7a94-b8db-b79d-008f60368f16
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718479(v=AX.60)
ms:contentKeyID: 49706765
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmPositionUnionAgreement Upgrade Script [AX 2012]


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
<td><p>updateHcmPositionUnionAgreement</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records in the HcmPositionUnionAgreement from PRL_PayGrids and Del_hrpPartyPositionTableRelationship table.</p></td>
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
<td><p>DEL_EMPLTABLE</p></td>
</tr>
<tr class="even">
<td><p>DEL_HRPPARTYPOSITIONTABLERELATIONSHIP</p></td>
</tr>
<tr class="odd">
<td><p>HCMPOSITION</p></td>
</tr>
<tr class="even">
<td><p>HCMPOSITIONUNIONAGREEMENT</p></td>
</tr>
<tr class="odd">
<td><p>HCMUNIONAGREEMENT</p></td>
</tr>
<tr class="even">
<td><p>PRL_UNIONGRID</p></td>
</tr>
<tr class="odd">
<td><p>PRLEMPLOYEEUSFEDERALTAXSETUP</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_HrpPartyPositionTableRelationship</p></th>
<th><p>To Table: HcmPositionUnionAgreement</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PositionID</p></td>
<td><p>Position</p></td>
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
<th><p>From Table: PRL_UnionGrid</p></th>
<th><p>To Table: HcmPositionUnionAgreement</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Agreement</p></td>
<td><p>Union</p></td>
</tr>
<tr class="even">
<td><p>FromDate</p></td>
<td><p>ValidFrom</p></td>
</tr>
<tr class="odd">
<td><p>ToDate</p></td>
<td><p>ValidTo</p></td>
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
<td><p>HcmPositionUnionAgreement</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

