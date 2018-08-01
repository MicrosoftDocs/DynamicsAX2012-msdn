---
title: ReleaseUpdateDB60_Ledger.allowNoDupClaimPerRGRegstrDateIdx_IN
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupClaimPerRGRegstrDateIdx_IN
ms:assetid: 67f4fbc9-af63-06a3-3035-a386621525b9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685615(v=AX.60)
ms:contentKeyID: 49708816
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupClaimPerRGRegstrDateIdx\_IN 


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
<td><p>allowNoDupClaimPerRGRegstrDateIdx_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the RGRegisterDateIdx index in the ClaimPercentage_IN table not to allow for duplicate records.</p></td>
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
<td><p>ClaimPercentage_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the surrogate key fields of the TaxComponentTable with the value of the RecId field of the tables. The RGRegisterDateIdx index is reset not to allow duplicate records.

  


