---
title: ReleaseUpdateDB60_Ledger.allowNoDupEximIncentiveSchemeData_INInce Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupEximIncentiveSchemeData_INInce Upgrade Script
ms:assetid: 5f3089bc-e2c3-2e6d-dc7f-d48f5576d3a6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719023(v=AX.60)
ms:contentKeyID: 49708563
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupEximIncentiveSchemeData\_INInce Upgrade Script 


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
<td><p>allowNoDupEximIncentiveSchemeData_INInce</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the IncentiveSchemeIdx index in the EximIncentiveSchemeData_IN table not to allow duplicate records.</p></td>
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
<td><p>EXIMINCENTIVESCHEMEDATA_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the EximIncentiveSchemeGroup surrogate key fields with the value of the RecId field of the tables, the IncentiveSchemeIdx index is reset to not allow duplicate records.

  


