---
title: ReleaseUpdateDB60_Ledger.updateTaxGroups_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateTaxGroups_BR Upgrade Script
ms:assetid: 85dc0d11-80d6-08fc-a65d-c9b63cb35635
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686045(v=AX.60)
ms:contentKeyID: 49709496
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateTaxGroups\_BR Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateTaxGroups_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Update tax tables with the surrogate key of the TaxationCodeTable_BR table.</p></td>
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
<td><p>TaxGroupData</p></td>
</tr>
<tr class="even">
<td><p>TaxOnItem</p></td>
</tr>
<tr class="odd">
<td><p>TaxTable</p></td>
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
<td><p>TaxGroupData</p></td>
<td><p>del_TaxationCode_BR</p></td>
</tr>
<tr class="even">
<td><p>TaxOnItem</p></td>
<td><p>del_spedTaxCode</p></td>
</tr>
<tr class="odd">
<td><p>TaxTable</p></td>
<td><p>del_spedTaxCode</p></td>
</tr>
</tbody>
</table>

  


