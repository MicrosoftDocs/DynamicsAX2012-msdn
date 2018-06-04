---
title: ReleaseUpdateDB60_Ledger.allowDupTaxTurnOverLine_NLKeyIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxTurnOverLine_NLKeyIdx Upgrade Script
ms:assetid: f4d42f20-1f8a-1863-d7fb-ad1dff63fce2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737562(v=AX.60)
ms:contentKeyID: 49712254
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxTurnOverLine\_NLKeyIdx Upgrade Script 


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
<td><p>allowDupTaxTurnOverLine_NLKeyIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the KeyIdx index in the TaxTurnOverLine_NL table to allow for duplicate records.</p></td>
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
<td><p>TaxTurnOverLine_NL</p></td>
</tr>
</tbody>
</table>


## Remarks

The TurnOverID field is replaced with the new TaxTurnOverTable\_NL surrogate key field in the unique KeyIdx index. Initially, this field contains no value. Therefore, the index is set to allow for duplicate values before the field is updated with the value of the RecId field of the TaxTurnOverTable\_NL table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

