---
title: ReleaseUpdateDB60_Ledger.updateTaxData_TaxSubstitutionMarkup_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateTaxData_TaxSubstitutionMarkup_BR Upgrade Script
ms:assetid: ad2c6f0d-e806-81b3-6829-bac7abeed65f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686511(v=AX.60)
ms:contentKeyID: 49710466
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateTaxData\_TaxSubstitutionMarkup\_BR Upgrade Script 


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
<td><p>updateTaxData_TaxSubstitutionMarkup_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the field TaxSubstitutionMarkupValue from &lt;c&gt;TaxData&lt;/c&gt; table with the same value of TaxReductionPct_BR when field TaxSubstitution_BR &lt;c&gt;TaxTable&lt;/c&gt; is set to Markup.</p></td>
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
<td><p>TaxTable</p></td>
</tr>
<tr class="even">
<td><p>TaxData</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TaxData</p></th>
<th><p>To Table: TaxData</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TaxReductionPct_BR</p></td>
<td><p>TaxSubstitutionMarkupValue</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

