---
title: ReleaseUpdateDB41_Administration.updateEPGlobalParameters Upgrade Script
TOCTitle: ReleaseUpdateDB41_Administration.updateEPGlobalParameters Upgrade Script
ms:assetid: 19893d8d-677f-8fd4-902c-dbf198498e0a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718633(v=AX.60)
ms:contentKeyID: 49706920
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Administration.updateEPGlobalParameters Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_Administration</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateEPGlobalParameters</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies data from the DEL_EPParameters table to the EPGlobalParameters table.</p></td>
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
<td><p>Administration</p></td>
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
<td><p>EPGlobalParameters</p></td>
</tr>
<tr class="even">
<td><p>DEL_EPParameters</p></td>
</tr>
</tbody>
</table>


## Remarks

The DEL\_EPParameters table has one row per company, while the EPGlobalParamaters table has one row for all companies. Data must therefore be compressed from the older table. The fields in the EPGlobalParameter table will be filled with values from the default company.

Note that this job is a shared job. As such, it will be run only in company DAT. Transfers the EPInitialSearchResultDisplayCount, EPOverflowSearchResultDisplayCount, EPSearchDebugMode, and DevelopmentSiteId fields.

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
<td><p>EPGlobalParameters</p></td>
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
<td><p>DEL_EPParameters</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


