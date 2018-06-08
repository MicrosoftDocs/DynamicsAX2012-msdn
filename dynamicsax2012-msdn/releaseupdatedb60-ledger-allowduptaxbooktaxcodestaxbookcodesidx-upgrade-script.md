---
title: ReleaseUpdateDB60_Ledger.allowDupTaxBookTaxCodesTaxBookCodesIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxBookTaxCodesTaxBookCodesIdx Upgrade Script
ms:assetid: 83e180fd-37ae-af9e-2ee7-796872f09b82
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685988(v=AX.60)
ms:contentKeyID: 49709442
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxBookTaxCodesTaxBookCodesIdx Upgrade Script 


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
<td><p>allowDupTaxBookTaxCodesTaxBookCodesIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TaxBookCodesIdx index in the TaxBookTaxCodes table to allow for duplicate records.</p></td>
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
<td><p>TaxBookTaxCodes</p></td>
</tr>
</tbody>
</table>


## Remarks

The TaxBook field is replaced with the new TaxBookTable surrogate key field in the unique TaxBookCodesIdx index. Initially, this field contains no value. Therefore, the index is set to allow for duplicate values before the field is updated with the value of the RecId field of the TaxBookTable table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

