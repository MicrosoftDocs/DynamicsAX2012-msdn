---
title: ReleaseUpdateDB60_Ledger.allowDupClaimPercentage_INRGRegisterDate
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupClaimPercentage_INRGRegisterDate
ms:assetid: e0084a99-6b28-7e58-ff34-3381421c3c4c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737285(v=AX.60)
ms:contentKeyID: 49711727
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupClaimPercentage\_INRGRegisterDate 


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
<td><p>allowDupClaimPercentage_INRGRegisterDate</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;RGRegisterDateIdx&lt;/c&gt; in the table &lt;c&gt;ClaimPercentage_IN&lt;/c&gt; to allow duplicate records.</p></td>
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
<td><p>CLAIMPERCENTAGE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The TaxComponent is replaced with the new surrogate key field TaxComponentTable in the unique index RGRegisterDateIdx. Also, the FromDate and ToDate fields are replaced with the Dateefeectivity fields ValidFrom and ValidTo. Initially these fields contains no values. So the index is set to allow duplicates before the field is updated with the value of the RecId's of the corresponding tables.

  


