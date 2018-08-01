---
title: ReleaseUpdateDB60_Basic.updateTaxItemGroupHeading Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateTaxItemGroupHeading Upgrade Script
ms:assetid: 8b599f8d-70a0-3acf-aef9-697b5690f864
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736431(v=AX.60)
ms:contentKeyID: 49709620
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateTaxItemGroupHeading Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateTaxItemGroupHeading</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the TaxItemGroupHeading table with the records that are created by using the pre-upgrade data.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>TaxItemGroupHeading</p></td>
</tr>
</tbody>
</table>


## Remarks

The upgrade looks at the sales tax codes in each item sales tax group and checks the tax code type. If all the codes in the item sales tax group have the same tax code type, the reporting type will be set to that type. If one or more sales tax code types on the codes within the group are different, the reporting type will be set to blank.

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
<td><p>TaxItemGroupHeading</p></td>
<td><p>EUSalesListType</p></td>
<td><p>EUSalesListType</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

