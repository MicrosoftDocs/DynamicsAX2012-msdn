---
title: ReleaseUpdateDB60_Ledger.allowDupTaxSetOffRuleCompColumnIdx_IN
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxSetOffRuleCompColumnIdx_IN
ms:assetid: 19275d3d-4c77-c7f8-b910-b9ac72f27456
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718626(v=AX.60)
ms:contentKeyID: 49706910
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxSetOffRuleCompColumnIdx\_IN 


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
<td><p>allowDupTaxSetOffRuleCompColumnIdx_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ComponentColumnIdx and ComponentTypeSetOffComponentTypeIdx indexes in the TaxSetOffRule_IN table to allow for duplicate records.</p></td>
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
<td><p>TaxSetOffRule_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The Component field is replaced with the new TaxComponentTable surrogate key field in the ComponentColumnIdx unique index. Initially this field contains no value. So the index is set to allow for duplicates before the field is updated with the value of the record ID field in the TaxComponentTable\_IN table. The Component field is replaced with the new TaxComponentTable and TaxComponentTableSetoff surrogate key fields in the ComponentColumnIdx and ComponentTypeSetOffComponentTypeIdx unique indexes. Initially this field contains no value. So the index is set to allow for duplicates before the field is updated with the value of the record ID field of the TaxComponentTable\_IN table.

  


