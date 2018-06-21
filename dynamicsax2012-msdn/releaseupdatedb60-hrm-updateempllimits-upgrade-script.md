---
title: ReleaseUpdateDB60_HRM.updateEmplLimits Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateEmplLimits Upgrade Script
ms:assetid: b6d93d25-4fba-fffb-5293-df48078918e6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737032(v=AX.60)
ms:contentKeyID: 49710714
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateEmplLimits Upgrade Script [AX 2012]


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
<td><p>updateEmplLimits</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates the employee limits which are defined on the Employees to the new signing limit model.</p></td>
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
<td><p>SRM</p></td>
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
<td><p>HRPApprovedLimit</p></td>
</tr>
<tr class="even">
<td><p>HRPApprovedLimitAmount</p></td>
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
<th><p>From Table: DEL_HRPLimitTableRelationship</p></th>
<th><p>To Table: HRPApprovedLimit</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>FromDateTime</p></td>
<td><p>ValidFrom</p></td>
</tr>
<tr class="even">
<td><p>ToDateTime</p></td>
<td><p>ValidTo</p></td>
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
<th><p>From Table: DEL_HRPLimitTypeTable</p></th>
<th><p>To Table: HRPApprovedLimit</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LimitType</p></td>
<td><p>SigningLimitType</p></td>
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
<th><p>From Table: DEL_HRPLimitTableRelationship</p></th>
<th><p>To Table: HRPApprovedLimitAmount</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LimitValue</p></td>
<td><p>Amount</p></td>
</tr>
<tr class="even">
<td><p>CurrencyCode</p></td>
<td><p>Currency</p></td>
</tr>
<tr class="odd">
<td><p>DataAreaId</p></td>
<td><p>CurrencyDataAreaID</p></td>
</tr>
<tr class="even">
<td><p>FromDateTime</p></td>
<td><p>ValidFrom</p></td>
</tr>
<tr class="odd">
<td><p>ToDateTime</p></td>
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
<td><p>HRPApprovedLimit</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>HRPApprovedLimitAmount</p></td>
<td><p></p></td>
<td><p></p></td>
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
<td><p>DEL_HRPLimitTableRelationship</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DEL_HRPLimitTypeTable</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

