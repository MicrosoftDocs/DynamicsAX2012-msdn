---
title: ReleaseUpdateDB60_COS.updateAbsorptionCostDimensions_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_COS.updateAbsorptionCostDimensions_BR Upgrade Script
ms:assetid: 93bc4570-5d95-5dc4-4b9a-ca3c63240a35
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686125(v=AX.60)
ms:contentKeyID: 49709829
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_COS.updateAbsorptionCostDimensions\_BR Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_COS</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateAbsorptionCostDimensions_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Converts dimension and ledger accounts to the dimension framework.</p></td>
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
<td><p>Cost accounting</p></td>
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
<td><p>ACOJournalTransOverhead_BR</p></td>
</tr>
<tr class="even">
<td><p>ACOProdOverHeadCostTrans_BR</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttribute</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttributeDirCategory</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttributeLevelValue</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttributeValue</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttributeValueCombination</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttributeValueCombinationStatus</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttributeValueGroup</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttributeValueGroupCombination</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttributeValueGroupStatus</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttributeValueSet</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttributeValueSetItem</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttributeSet</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttributeSetItem</p></td>
</tr>
<tr class="even">
<td><p>DimensionFinancialTag</p></td>
</tr>
<tr class="odd">
<td><p>DimensionHierarchy</p></td>
</tr>
<tr class="even">
<td><p>DimensionHierarchyLevel</p></td>
</tr>
<tr class="odd">
<td><p>DimensionValueGroupJournalControlStatus</p></td>
</tr>
<tr class="even">
<td><p>FinancialTagCategory</p></td>
</tr>
<tr class="odd">
<td><p>LedgerParameters</p></td>
</tr>
<tr class="even">
<td><p>MainAccount</p></td>
</tr>
<tr class="odd">
<td><p>Ledger</p></td>
</tr>
</tbody>
</table>


## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ACOProdOverHeadCostTrans_BR</p></td>
<td><p>LedgerDimension</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>ACOJournalTransOverHead_BR</p></td>
<td><p>LedgerDimension</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>ACOJournalTransOverHead_BR</p></td>
<td><p>DimensionAttributeValue</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ACOProdOverHeadCostTrans_BR</p></td>
<td><p>AccountNum</p></td>
</tr>
<tr class="even">
<td><p>ACOJournalTransOverHead_BR</p></td>
<td><p>AccountNum</p></td>
</tr>
<tr class="odd">
<td><p>ACOJournalTransOverHead_BR</p></td>
<td><p>Dimension</p></td>
</tr>
</tbody>
</table>

  


