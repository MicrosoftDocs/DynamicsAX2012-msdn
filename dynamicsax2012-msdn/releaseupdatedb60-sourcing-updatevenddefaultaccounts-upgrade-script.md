---
title: ReleaseUpdateDB60_Sourcing.updateVendDefaultAccounts Upgrade Script
TOCTitle: ReleaseUpdateDB60_Sourcing.updateVendDefaultAccounts Upgrade Script
ms:assetid: f475c242-2502-5060-8e5d-4be9d868820a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737507(v=AX.60)
ms:contentKeyID: 49712201
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Sourcing.updateVendDefaultAccounts Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Sourcing</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateVendDefaultAccounts</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the LedgerDimension field of the VendDefaultAccounts table with the corresponding value from the RecId field of the DimensionAttributeValueCombination table.</p></td>
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
<td><p>SRM</p></td>
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
<td><p>DimensionAttributeValueCombinationStatus</p></td>
</tr>
<tr class="even">
<td><p>LedgerBasic</p></td>
</tr>
<tr class="odd">
<td><p>VendDefaultAccounts</p></td>
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
</tbody>
</table>


## Remarks

This method is part of the overall financial dimensions work in this release.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

