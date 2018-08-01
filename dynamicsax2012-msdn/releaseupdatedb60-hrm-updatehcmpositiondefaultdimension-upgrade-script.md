---
title: ReleaseUpdateDB60_HRM.updateHcmPositionDefaultDimension Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmPositionDefaultDimension Upgrade Script
ms:assetid: 8e86ba39-7f40-cb33-9dab-a35eb91c9b94
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736511(v=AX.60)
ms:contentKeyID: 49709700
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmPositionDefaultDimension Upgrade Script 


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
<td><p>updateHcmPositionDefaultDimension</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts data into the HcmPositionDefaultDimension table from the HRPPartyPositionTableRelationship table.</p></td>
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
<td><p>CompanyInfo</p></td>
</tr>
<tr class="even">
<td><p>DEL_HRPPartyPositionTableRelationship</p></td>
</tr>
<tr class="odd">
<td><p>HcmPosition</p></td>
</tr>
<tr class="even">
<td><p>HcmPositionDefaultDimension</p></td>
</tr>
</tbody>
</table>


## Remarks

For each position, the DefaultDimetion value from the latest PositionDetail record is upgraded as the DefaultDimension value for the position.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_HRPPartyPositionTableRelationship</p></th>
<th><p>To Table: HcmPositionDefaultDimension</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dimension</p></td>
<td><p>DefaultDimension</p></td>
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
<td><p>HcmPositionDefaultDimension</p></td>
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
<td><p>DEL_HRPPartyPositionTableRelationship</p></td>
<td><p>DefualtDimension</p></td>
</tr>
</tbody>
</table>

  


