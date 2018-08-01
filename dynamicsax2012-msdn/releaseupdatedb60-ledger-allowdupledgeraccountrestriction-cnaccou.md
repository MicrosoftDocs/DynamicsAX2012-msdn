---
title: ReleaseUpdateDB60_Ledger.allowDupLedgerAccountRestriction_CNAccou
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupLedgerAccountRestriction_CNAccou
ms:assetid: c030019f-ad51-3e23-c802-7af2b99d5c2b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686770(v=AX.60)
ms:contentKeyID: 49710968
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupLedgerAccountRestriction\_CNAccou 


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
<td><p>allowDupLedgerAccountRestriction_CNAccou</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;AccountRestrictionIdx&lt;/c&gt; in the table &lt;c&gt;LedgerAccountRestriction_CN&lt;/c&gt; to allow duplicate records.</p></td>
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
<td><p>LEDGERACCOUNTRESTRICTION_CN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the surrogate key field LedgerAccountRestriction\_CN with the value of the RecId field of the table LedgerAccountRestriction\_CN, the index AccountRestrictionIdx is reset not to allow duplicate records.

  


