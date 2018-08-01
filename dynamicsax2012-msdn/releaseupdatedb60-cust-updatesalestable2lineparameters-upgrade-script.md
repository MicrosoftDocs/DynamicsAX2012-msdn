---
title: ReleaseUpdateDB60_Cust.updateSalesTable2LineParameters Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateSalesTable2LineParameters Upgrade Script
ms:assetid: 63d87a27-7a12-3b55-15b4-b94ccf7543ff
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719145(v=AX.60)
ms:contentKeyID: 49708684
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateSalesTable2LineParameters Upgrade Script 


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
<td><p>updateSalesTable2LineParameters</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts a record for &lt;c&gt;DlvTerm&lt;/c&gt; field into the &lt;c&gt;SalesTable2LineParameters&lt;/c&gt; table and sets its' &lt;c&gt;Table2LineUpdate&lt;/c&gt; field to TradeTable2LineUpdate::Never.</p></td>
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
<td><p>SalesTable2LineParameters</p></td>
</tr>
</tbody>
</table>


## Remarks

The record will only be created if other records in \<c\>SalesTable2LineParameters\</c\> table for current legal entity exist.

  


