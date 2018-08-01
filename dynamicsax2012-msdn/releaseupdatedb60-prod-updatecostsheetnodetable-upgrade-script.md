---
title: ReleaseUpdateDB60_Prod.updateCostSheetNodeTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Prod.updateCostSheetNodeTable Upgrade Script
ms:assetid: dbd66fb4-607d-6c39-9340-eb9ee4f78457
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737199(v=AX.60)
ms:contentKeyID: 49711642
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Prod.updateCostSheetNodeTable Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Prod</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCostSheetNodeTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the dimensions of the CostSheetNodeTable table with the corresponding value from the RecId field of the DimensionAttributeValueSet table.</p></td>
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
<td><p>Production</p></td>
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
<td><p>CostSheetNodeTable</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttribute</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttributeDirCategory</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttributeLevelValue</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttributeValue</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttributeValueCombination</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttributeValueCombinationStatus</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttributeValueGroup</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttributeValueGroupCombination</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttributeValueGroupStatus</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttributeValueSet</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttributeValueSetItem</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttributeSet</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttributeSetItem</p></td>
</tr>
<tr class="odd">
<td><p>DimensionFinancialTag</p></td>
</tr>
<tr class="even">
<td><p>DimensionHierarchy</p></td>
</tr>
<tr class="odd">
<td><p>DimensionHierarchyLevel</p></td>
</tr>
<tr class="even">
<td><p>DimensionValueGroupJournalControlStatus</p></td>
</tr>
<tr class="odd">
<td><p>FinancialTagCategory</p></td>
</tr>
<tr class="even">
<td><p>LedgerParameters</p></td>
</tr>
<tr class="odd">
<td><p>MainAccount</p></td>
</tr>
</tbody>
</table>

  


