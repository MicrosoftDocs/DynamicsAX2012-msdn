---
title: ReleaseUpdateDB60_Basic.updateTaxReport770Table_IT Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateTaxReport770Table_IT Upgrade Script
ms:assetid: 244b03aa-b1d3-e8e8-19c7-56795cbfab3f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684992(v=AX.60)
ms:contentKeyID: 49707194
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateTaxReport770Table\_IT Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateTaxReport770Table_IT</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the TaxReport770Table_IT table by updating the ExceptionalEvent field to use the new enumeration value for exceptional events.</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>TaxReport770Table_IT</p></td>
</tr>
</tbody>
</table>


## Remarks

The TaxReport770ExceptionalEvent\_IT::ExceptionalCircumstances enumeration element had its value changed from 5 to 9. This upgrade script makes sure the database is updated, by moving values from the TaxReport770ExceptionalEvent\_IT::DEL\_ExceptionalCircumstances enumeration element to the TaxReport770ExceptionalEvent\_IT::ExceptionalCircumstances enumeration element.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

