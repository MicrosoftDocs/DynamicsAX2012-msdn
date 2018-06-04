---
title: ReleaseUpdateDB60_HRM.updateHcmUnionAgreementDuration Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmUnionAgreementDuration Upgrade Script
ms:assetid: de9d6ead-d7d2-6989-9bad-20a278d459e7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737238(v=AX.60)
ms:contentKeyID: 49711680
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmUnionAgreementDuration Upgrade Script 


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
<td><p>updateHcmUnionAgreementDuration</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmUnionAgreementDuration table from the PRL_PayGrids table.</p></td>
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
<td><p>HCMUNIONAGREEMENTDURATION</p></td>
</tr>
<tr class="even">
<td><p>PRL_PAYGRIDS</p></td>
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
<th><p>From Table: PRL_PayGrids</p></th>
<th><p>To Table: HcmUnionAgreementDuration</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Agreement</p></td>
<td><p>UnionAgreement</p></td>
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
<td><p>HcmUnionAgreementDuration</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

