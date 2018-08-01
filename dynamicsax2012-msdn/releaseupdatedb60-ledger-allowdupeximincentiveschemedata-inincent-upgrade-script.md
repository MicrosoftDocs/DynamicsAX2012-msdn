---
title: ReleaseUpdateDB60_Ledger.allowDupEximIncentiveSchemeData_INIncent Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupEximIncentiveSchemeData_INIncent Upgrade Script
ms:assetid: 35925bc2-cb74-c03e-246f-2ebd58f66c52
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685148(v=AX.60)
ms:contentKeyID: 49707600
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupEximIncentiveSchemeData\_INIncent Upgrade Script 


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
<td><p>allowDupEximIncentiveSchemeData_INIncent</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the IncentiveSchemeIdx index in the EximIncentiveSchemeData_IN table to allow duplicate records.</p></td>
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

The IncentiveSchemeGroup field is replaced with the new EximIncentiveSchemeGroup surrogate key field in the unique IncentiveSchemeIdx index. Initially the EximIncentiveSchemeGroup field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields of the EximIncentiveSchemeGroup\_IN table.

  


