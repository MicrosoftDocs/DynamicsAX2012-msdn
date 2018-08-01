---
title: ReleaseUpdateDB60_Ledger.allowNoDupTaxSetOffRuleCompColumnIdx_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupTaxSetOffRuleCompColumnIdx_IN Upgrade Script
ms:assetid: e7895078-dbee-66b9-b445-fab5cb2c6416
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719826(v=AX.60)
ms:contentKeyID: 49711899
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupTaxSetOffRuleCompColumnIdx\_IN Upgrade Script 


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
<td><p>allowNoDupTaxSetOffRuleCompColumnIdx_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ComponentColumnIdx and ComponentTypeSetOffComponentTypeIdx indexes in the TaxSetOffRule_IN table not to allow for duplicate records.</p></td>
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
<td><p>TaxSetOffRule_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the TaxComponentTable surrogate key field with the value of the RecId field in the TaxComponentTable\_IN table, the ComponentColumnIdx and ComponentTypeSetOffComponentTypeIdx index is reset not to allow for duplicate records.

  


