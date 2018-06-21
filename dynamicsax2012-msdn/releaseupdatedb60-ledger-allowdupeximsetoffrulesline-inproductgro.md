---
title: ReleaseUpdateDB60_Ledger.allowDupEximSetOffRulesLine_INProductGro
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupEximSetOffRulesLine_INProductGro
ms:assetid: f5e1e56e-a436-ab4e-dcd4-17cb850022fd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737550(v=AX.60)
ms:contentKeyID: 49712244
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupEximSetOffRulesLine\_INProductGro [AX 2012]


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
<td><p>allowDupEximSetOffRulesLine_INProductGro</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;ProductGroupSetOffRulesIdx&lt;/c&gt; in the table &lt;c&gt;EximSetOffRulesLine_IN&lt;/c&gt; to allow duplicate records.</p></td>
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
<td><p>EXIMSETOFFRULESLINE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The ProductGroup field is replaced with the new surrogate key field EximProductGroupTable is replaced in ProductGroupSetOffRulesIdx. Initially the EximProductGroupTable field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields of the table EximProductGroupTable\_IN.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

