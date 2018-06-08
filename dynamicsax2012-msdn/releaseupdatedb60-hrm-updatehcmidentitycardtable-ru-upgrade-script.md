---
title: ReleaseUpdateDB60_HRM.updateHcmIdentityCardTable_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmIdentityCardTable_RU Upgrade Script
ms:assetid: 79ab4102-9325-9a8c-6b76-f96a7980983b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719409(v=AX.60)
ms:contentKeyID: 49709200
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmIdentityCardTable\_RU Upgrade Script 


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
<td><p>updateHcmIdentityCardTable_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmIdentityCardTable_RU table from the IdentityCardTable_RU table.</p></td>
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
<td><p>HcmIdentityCardTable_RU</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will discard duplicate records if the IdentityCardCode field of the IdentityCardTable\_RU table is identical.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: IdentityCardTable_RU</p></th>
<th><p>To Table: HcmIdentityCardTable_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IdentityCardCode</p></td>
<td><p>Code</p></td>
</tr>
<tr class="even">
<td><p>IdentityCardNamemiddle</p></td>
<td><p>MiddleName</p></td>
</tr>
<tr class="odd">
<td><p>IdentityCardNameFull</p></td>
<td><p>FullName</p></td>
</tr>
<tr class="even">
<td><p>IdentityCardNameShort</p></td>
<td><p>ShortName</p></td>
</tr>
<tr class="odd">
<td><p>IdentityCardPatternSeries</p></td>
<td><p>PatternSeries</p></td>
</tr>
<tr class="even">
<td><p>IdentityCardIssueAge</p></td>
<td><p>IssueAge</p></td>
</tr>
<tr class="odd">
<td><p>IdentityCardPatternNumber</p></td>
<td><p>PatternNumber</p></td>
</tr>
<tr class="even">
<td><p>IdentityCardTypePf</p></td>
<td><p>TypePf</p></td>
</tr>
<tr class="odd">
<td><p>IdentityCardNamePf</p></td>
<td><p>NamePf</p></td>
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
<th><p>From Table:</p></th>
<th><p>To Table:</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
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
<td><p>HcmIdentityCardTable_RU</p></td>
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
<td><p>IdentityCardTable_RU</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

