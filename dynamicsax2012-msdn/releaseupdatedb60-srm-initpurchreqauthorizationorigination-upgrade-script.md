---
title: ReleaseUpdateDB60_Srm.initPurchReqAuthorizationOrigination Upgrade Script
TOCTitle: ReleaseUpdateDB60_Srm.initPurchReqAuthorizationOrigination Upgrade Script
ms:assetid: e1807fdb-5951-55ce-6eaa-176dfd97747c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737300(v=AX.60)
ms:contentKeyID: 49711742
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Srm.initPurchReqAuthorizationOrigination Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Srm</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>initPurchReqAuthorizationOrigination</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Initializes the values in the PurchReqAuthorizationOrigination table.</p></td>
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
<td><p>PurchReqAuthorizationOrigination</p></td>
</tr>
</tbody>
</table>


## Remarks

A PurchReqAuthorizationOrigination table has been introduced to hold data which was in the EmplOnBehalf table in the last release.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: EmplOnBehalf</p></th>
<th><p>To Table: PurchReqAuthorizationOrigination</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SpecificReporting</p></td>
<td><p>SpecifcReporting</p></td>
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
<td><p>PurchReqAuthorizationOrigination</p></td>
<td><p>Originator</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqAuthorizationOrigination</p></td>
<td><p>Requisitioner</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqAuthorizationOrigination</p></td>
<td><p>SpecificReporting</p></td>
<td><p>PurchReqAuthorizationSpecificReporting</p></td>
</tr>
<tr class="even">
<td><p>PurchReqAuthorizationOrigination</p></td>
<td><p>ValidTo</p></td>
<td><p>ValidToDate</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqAuthorizationOrigination</p></td>
<td><p>ValidFrom</p></td>
<td><p>ValidFromDate</p></td>
</tr>
<tr class="even">
<td><p>PurchReqAuthorizationOrigination</p></td>
<td><p>IsAdminCreated</p></td>
<td><p>NoYesId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

