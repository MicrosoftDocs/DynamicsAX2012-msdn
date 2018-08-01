---
title: ReleaseUpdateDB60_Trv.updateAdminCustomFieldsCopyToAllLE Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateAdminCustomFieldsCopyToAllLE Upgrade Script
ms:assetid: ee207e0b-137e-ad9a-7144-20e14593849c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719986(v=AX.60)
ms:contentKeyID: 49712057
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateAdminCustomFieldsCopyToAllLE Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Trv</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateAdminCustomFieldsCopyToAllLE</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Enables all existing custom field entries to be available to all legal entities in the system.</p></td>
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
<td><p>Expense management</p></td>
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
<td><p>TrvAdminCustomFields</p></td>
</tr>
</tbody>
</table>


## Remarks

This script is used to copy the existing admin custom settings to all the legal entities.

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
<td><p>TrvAdminCustomFields</p></td>
<td><p>LegalEntity</p></td>
<td><p>RefRecId</p></td>
</tr>
</tbody>
</table>

  


