---
title: ReleaseUpdateDB60_Ledger.allowNoDupEximSetOffRulesTable_INIncenti
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupEximSetOffRulesTable_INIncenti
ms:assetid: 4d0f8b74-f469-fa81-aaee-9e249562ab4f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685426(v=AX.60)
ms:contentKeyID: 49708131
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupEximSetOffRulesTable\_INIncenti 


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
<td><p>allowNoDupEximSetOffRulesTable_INIncenti</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;IncentiveSchemeDataIdx&lt;/c&gt; in the table &lt;c&gt;EximSetOffRulesTable_IN&lt;/c&gt; not to allow duplicate records.</p></td>
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
<td><p>EXIMSETOFFRULESTABLE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the surrogate key field EximDEPBSchemesTable RecId field of the table EximDEPBSchemesTable\_IN, the index IncentiveSchemeDataIdx is reset not to allow duplicate records.

  


