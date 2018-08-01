---
title: ReleaseUpdateDB60_EMS.updateEMSTableDefaults Upgrade Script
TOCTitle: ReleaseUpdateDB60_EMS.updateEMSTableDefaults Upgrade Script
ms:assetid: f3870a46-0913-1a2b-d943-23e20d53c3b1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737516(v=AX.60)
ms:contentKeyID: 49712210
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_EMS.updateEMSTableDefaults Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_EMS</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateEMSTableDefaults</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the default values for EMS tables.</p></td>
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
<td><p>Environment</p></td>
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
<td><p>EMSFlow</p></td>
</tr>
<tr class="even">
<td><p>EMSConversion</p></td>
</tr>
<tr class="odd">
<td><p>EMSProcessRelation</p></td>
</tr>
<tr class="even">
<td><p>EMSSubstance</p></td>
</tr>
<tr class="odd">
<td><p>EMSSubstanceCategory</p></td>
</tr>
<tr class="even">
<td><p>DirPartyTable</p></td>
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
<td><p>EMSSubstanceCategory</p></td>
<td><p>MapColor</p></td>
<td><p>EMSMapColor</p></td>
</tr>
<tr class="even">
<td><p>EMSSubstance</p></td>
<td><p>MapColor</p></td>
<td><p>EMSMapColor</p></td>
</tr>
<tr class="odd">
<td><p>EMSConversion</p></td>
<td><p>ConversionType</p></td>
<td><p>EMSDirection</p></td>
</tr>
<tr class="even">
<td><p>EMSFlow</p></td>
<td><p>EquityShare</p></td>
<td><p>Percent</p></td>
</tr>
<tr class="odd">
<td><p>EMSProcessRelation</p></td>
<td><p>Party</p></td>
<td><p>DirPartyRecId</p></td>
</tr>
</tbody>
</table>

  


