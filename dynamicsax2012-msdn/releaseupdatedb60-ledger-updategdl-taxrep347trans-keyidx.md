---
title: ReleaseUpdateDB60_Ledger.updateGDL_TaxRep347Trans_KeyIdx
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_TaxRep347Trans_KeyIdx
ms:assetid: 5adc6e7f-8520-e6c3-652f-822ed586106d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736299(v=AX.60)
ms:contentKeyID: 49708471
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_TaxRep347Trans\_KeyIdx [AX 2012]


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
<td><p>updateGDL_TaxRep347Trans_KeyIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Removes duplicating &lt;c&gt;TaxReport347Trans&lt;/c&gt; records and aggregates Amount and AmountInCash values into one record. This is done in order to ensure uniqueness of the natural key (KeyIdx) of the &lt;c&gt;TaxReport347Trans&lt;/c&gt; table.</p></td>
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
<td><p>TaxReport347Trans</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

