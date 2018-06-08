---
title: ReleaseUpdateDB60_Ledger.allowNoDupClaimPerRGRegstrDateIdx_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupClaimPerRGRegstrDateIdx_IN Upgrade Script
ms:assetid: b71900ec-139c-19f4-9e94-c4eb3f5d05a0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737049(v=AX.60)
ms:contentKeyID: 49710731
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupClaimPerRGRegstrDateIdx\_IN Upgrade Script 


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

After updating the TaxComponentTable surrogate key fields with the value of the record ID field of the ClaimPercentage\_IN table, the RGRegisterDateIdx index is reset not to allow for duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

