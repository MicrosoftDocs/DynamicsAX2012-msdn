﻿---
title: ReleaseUpdateDB60_Ledger.allowDupTaxWithholdOnItem_THTaxItemCodeI Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxWithholdOnItem_THTaxItemCodeI Upgrade Script
ms:assetid: a6b1ef17-3868-d2a5-bcd2-878df7326378
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736851(v=AX.60)
ms:contentKeyID: 49710282
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxWithholdOnItem\_THTaxItemCodeI Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowDupTaxWithholdOnItem_THTaxItemCodeI</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TaxItemCodeIdx index in the TaxWithholdOnItem_TH table to allow for duplicate records.</p></td>
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
<td><p>Ledger</p></td>
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
<td><p>TaxWithholdOnItem_TH</p></td>
</tr>
</tbody>
</table>


## Remarks

The TaxWithholdItemGroup field is replaced with the new TaxWithholdItemGroupHeading\_TH surrogate key field in the unique TaxItemCodeIdx index. Initially, this field contains no value. Therefore, the index is set to allow for duplicate values before the field is updated with the value of the RecId field of the TaxWithholdItemGroupHeading\_TH table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

