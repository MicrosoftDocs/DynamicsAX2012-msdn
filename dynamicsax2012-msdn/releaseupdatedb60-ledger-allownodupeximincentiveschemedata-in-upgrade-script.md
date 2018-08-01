---
title: ReleaseUpdateDB60_Ledger.allowNoDupEximIncentiveSchemeData_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupEximIncentiveSchemeData_IN Upgrade Script
ms:assetid: 4d4e6094-752a-4380-b162-84ab7e072104
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685432(v=AX.60)
ms:contentKeyID: 49708136
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupEximIncentiveSchemeData\_IN Upgrade Script 


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
<td><p>allowNoDupEximIncentiveSchemeData_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the IncentiveSchemeIdx index in the EximIncentiveSchemeData_IN table not to allow for duplicate records.</p></td>
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
<td><p>EximIncentiveSchemeData_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the EximIncentiveSchemeGroup surrogate key fields with the value of the record ID field in the EximIncentiveSchemeData\_IN table, the IncentiveSchemeIdx index is reset not to allow for duplicate records.

  


