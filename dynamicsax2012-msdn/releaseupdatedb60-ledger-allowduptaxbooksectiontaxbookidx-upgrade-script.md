---
title: ReleaseUpdateDB60_Ledger.allowDupTaxBookSectionTaxBookIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxBookSectionTaxBookIdx Upgrade Script
ms:assetid: 3e456b93-3764-99a1-d8a2-eb81fb2d845a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718760(v=AX.60)
ms:contentKeyID: 49707805
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxBookSectionTaxBookIdx Upgrade Script 


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
<td><p>allowDupTaxBookSectionTaxBookIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TaxBookIdx index in the TaxBookSection table to allow for duplicate records.</p></td>
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
<td><p>TaxBookSection</p></td>
</tr>
</tbody>
</table>


## Remarks

The TaxBookId field is replaced with the new TaxBook surrogate key field in the unique TaxBookIdx index. Initially, this field contains no value. Therefore, the index is set to allow for duplicate values before the field is updated with the value of the RecId field of the TaxBook table.

  


