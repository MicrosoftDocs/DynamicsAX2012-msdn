---
title: ReleaseUpdateDB60_Ledger.updateLedgerOpeningTrans_ES Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerOpeningTrans_ES Upgrade Script
ms:assetid: ea28a103-de5d-4d11-731d-51dbd251bf31
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719880(v=AX.60)
ms:contentKeyID: 49711954
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerOpeningTrans\_ES Upgrade Script 


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
<td><p>updateLedgerOpeningTrans_ES</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This script updates the LedgerDimension, OffsetLedgerDimension, and MainAccount fields in the LedgerOpeningTrans_ES table.</p></td>
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
<td><p>LedgerOpeningTrans_ES</p></td>
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

The AccountNum and OffsetAccount fields are replaced with the new LedgerDimension and OffsetLedgerDimension fields.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

