---
title: ReleaseUpdateDB60_Ledger.allowDupCustomsComponentTaxCodes_INTaxCo Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupCustomsComponentTaxCodes_INTaxCo Upgrade Script
ms:assetid: d2486665-0310-62c8-f1f5-33210cea536e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686975(v=AX.60)
ms:contentKeyID: 49711425
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupCustomsComponentTaxCodes\_INTaxCo Upgrade Script [AX 2012]


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
<td><p>allowDupCustomsComponentTaxCodes_INTaxCo</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TaxComponentTaxCodeIdx index in the CustomsComponentTaxCodes_IN table to allow duplicate records.</p></td>
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
<td><p>CUSTOMSCOMPONENTTAXCODES_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The TaxComponent field is replaced with the new TaxComponentTable surrogate key field in the unique TaxComponentTaxCodeIdx index. Initially the TaxComponentTable field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields of the CustomsComponentTaxCodes\_IN table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

