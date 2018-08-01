---
title: ReleaseUpdateDB60_Cust.allowNoDupEximDBKValues_IN
TOCTitle: ReleaseUpdateDB60_Cust.allowNoDupEximDBKValues_IN
ms:assetid: 9d244182-e04b-e7e5-fbe4-6145ceebb3a3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736620(v=AX.60)
ms:contentKeyID: 49710063
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.allowNoDupEximDBKValues\_IN 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupEximDBKValues_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TariffCodeIdx index in the EximDBKValues_IN table not to allow duplicate records.</p></td>
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
<td><p>Accounts receivable</p></td>
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
<td><p>EximDBKValues_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The ValidFrom and ValidTo values are inserted Initially these are date effective fields. So the index is set to allow duplicates before the field is updated with the values. The TariffCodeIdx index is reset not to allow duplicate records.

  


