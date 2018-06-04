---
title: ReleaseUpdateDB60_Prod.updateMarkupTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Prod.updateMarkupTable Upgrade Script
ms:assetid: c62e98e5-7527-587f-46bf-2cc88025dae9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719550(v=AX.60)
ms:contentKeyID: 49711118
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Prod.updateMarkupTable Upgrade Script 


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
<td><p>updateMarkupTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the CustomerLedgerDimension and VendorLedgerDimension fields of the MarkupTable table with the corresponding value from the RecId field of the DimensionAttributeValueCombination table.</p></td>
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
<td><p>Product management</p></td>
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
<td><p>DimensionAttribute</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttributeDirCategory</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttributeLevelValue</p></td>
</tr>
<tr class="even">
<td><p>DimensionAttributeSet</p></td>
</tr>
<tr class="odd">
<td><p>DimensionAttributeSetItem</p></td>
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
<td><p>MarkupTable</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

