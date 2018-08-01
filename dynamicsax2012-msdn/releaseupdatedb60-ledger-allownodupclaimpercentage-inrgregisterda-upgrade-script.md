---
title: ReleaseUpdateDB60_Ledger.allowNoDupClaimPercentage_INRGRegisterDa Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupClaimPercentage_INRGRegisterDa Upgrade Script
ms:assetid: 46b5b5bd-79b6-b068-0a10-7e3eb50613a4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718970(v=AX.60)
ms:contentKeyID: 49708004
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupClaimPercentage\_INRGRegisterDa Upgrade Script 


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
<td><p>allowNoDupClaimPercentage_INRGRegisterDa</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the RGRegisterDateIdx index in the ClaimPercentage_IN table to not allow duplicate records.</p></td>
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

After updating the TaxComponentTable surrogate key fields with the value of the RecId field of the tables, the RGRegisterDateIdx index is reset to not allow duplicate records.

  


