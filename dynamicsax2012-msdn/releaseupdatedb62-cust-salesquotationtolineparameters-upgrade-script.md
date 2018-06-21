---
title: ReleaseUpdateDB62_Cust .SalesQuotationToLineParameters Upgrade Script
TOCTitle: ReleaseUpdateDB62_Cust .SalesQuotationToLineParameters Upgrade Script
ms:assetid: 6d390f1e-8abc-6794-e51d-a13edc06873d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn702757(v=AX.60)
ms:contentKeyID: 65236213
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB62\_Cust .SalesQuotationToLineParameters Upgrade Script [AX 2012]


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB62_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>SalesQuotationToLineParameters</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts a record for &lt;c&gt;DlvTerm&lt;/c&gt; field into the &lt;c&gt;SalesQuotationToLineParameters&lt;/c&gt; table and sets its' &lt;c&gt;Table2LineUpdate&lt;/c&gt; field to TradeTable2LineUpdate::Never.</p></td>
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
<td><p>SalesQuotationToLineParameters</p></td>
</tr>
</tbody>
</table>


## Remarks

The record will only be created if other records in \<c\>SalesTable2LineParameters\</c\> table for current legal entity exist.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

