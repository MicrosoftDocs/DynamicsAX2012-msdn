---
title: ReleaseUpdateDB60_Ledger.allowDupClaimPercentage_INRGRegisterDate Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupClaimPercentage_INRGRegisterDate Upgrade Script
ms:assetid: 06273d44-2c6b-871a-b4d0-fc9403ea39b6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684736(v=AX.60)
ms:contentKeyID: 49706437
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupClaimPercentage\_INRGRegisterDate Upgrade Script [AX 2012]


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
<td><p>Updates the RGRegisterDateIdx index in the ClaimPercentage_IN table to allow duplicate records.</p></td>
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

The TaxComponent field is replaced with the new TaxComponentTable surrogate key field in the unique RGRegisterDateIdx index. Also, the FromDate and ToDate fields are replaced with the Dateefeectivity fields. Initially these fields contains no values. So the index is set to allow duplicates before the field is updated with the value of the record ID of the corresponding tables.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

