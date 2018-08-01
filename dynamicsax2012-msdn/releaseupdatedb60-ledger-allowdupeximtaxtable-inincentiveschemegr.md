---
title: ReleaseUpdateDB60_Ledger.allowDupEximTaxTable_INIncentiveSchemeGr
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupEximTaxTable_INIncentiveSchemeGr
ms:assetid: c9ba299e-3b49-e771-2b66-8809e0cdbbb1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719631(v=AX.60)
ms:contentKeyID: 49711197
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupEximTaxTable\_INIncentiveSchemeGr 


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
<td><p>allowDupEximTaxTable_INIncentiveSchemeGr</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;IncentiveSchemeTaxIdx&lt;/c&gt; in the table &lt;c&gt;EximTaxTable_IN&lt;/c&gt; to allow duplicate records.</p></td>
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
<td><p>EXIMTAXTABLE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The IncentiveSchemeGroup field is replaced with the new Reference field EximIncentiveSchemeGroup in the unique index IncentiveSchemeTaxIdx. Initially the EximIncentiveSchemeGroup field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields of the table EximIncentiveSchemeGroup\_IN.

  


