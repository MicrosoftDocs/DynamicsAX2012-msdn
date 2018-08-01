---
title: ReleaseUpdateDB60_Trv.updateDimensionsGlobalTables Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateDimensionsGlobalTables Upgrade Script
ms:assetid: 53e482fc-36f1-6aa8-3284-7e895e9aa94b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736131(v=AX.60)
ms:contentKeyID: 49708307
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateDimensionsGlobalTables Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Trv</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateDimensionsGlobalTables</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the Expense Management tables that are data area ID independent. It calls several private methods where the actual upgrade work is performed.</p></td>
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
<td><p>Expense management</p></td>
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
<td><p>TrvExpTable</p></td>
</tr>
<tr class="even">
<td><p>TrvExpTrans</p></td>
</tr>
<tr class="odd">
<td><p>TrvExpTrans_Proj</p></td>
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


## Remarks

The DEL\_Dimension field of the TrvExpTable table is upgraded to the DefaultDimension field. The DEL\_Dimension field of the TrvExpTrans table is upgraded to the DefaultDimension field. Currently, nothing is upgrade in the TrvExpTrans\_Prok table.- TODO after completing the Expense and Project integration.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TrvExpTable</p></th>
<th><p>To Table: TrvExpTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_Dimension</p></td>
<td><p>DefaultDimension</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TrvExpTrans</p></th>
<th><p>To Table: TrvExpTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_Dimension</p></td>
<td><p>DefaultDimension</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TrvExpTrans_Proj</p></th>
<th><p>To Table: TrvExpTrans_Proj</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


