---
title: ReleaseUpdateDB60_Trv.updateDimensionsNonGlobalTables Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateDimensionsNonGlobalTables Upgrade Script
ms:assetid: 55624b9d-b6af-530b-90b4-b1a0a5df43f6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736179(v=AX.60)
ms:contentKeyID: 49708354
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateDimensionsNonGlobalTables Upgrade Script 


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
<td><p>updateDimensionsNonGlobalTables</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the Expense Management tables that are data area ID dependent. It calls several private methods where the actual upgrade work is performed.</p></td>
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
<td><p>TrvPayMethod</p></td>
</tr>
<tr class="even">
<td><p>TrvCashAdvance</p></td>
</tr>
<tr class="odd">
<td><p>TrvCostType</p></td>
</tr>
<tr class="even">
<td><p>TrvExchSetup</p></td>
</tr>
<tr class="odd">
<td><p>TrvPartyEmployeeRelationship</p></td>
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


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TrvPayMethod</p></th>
<th><p>To Table: TrvPayMethod</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_SetOffAcc</p></td>
<td><p>OffsetLedgerDimension</p></td>
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
<th><p>From Table: TrvCashAdvance</p></th>
<th><p>To Table: TrvCashAdvance</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_Dimension</p></td>
<td><p>DefaultDimension</p></td>
</tr>
<tr class="even">
<td><p>Del_AccountNumber</p></td>
<td><p>AdvanceLedgerDimension</p></td>
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
<th><p>From Table: TrvCostType</p></th>
<th><p>To Table: TrvCostType</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_AccountNumber</p></td>
<td><p>LedgerDimension</p></td>
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
<th><p>From Table: TrvExchSetup</p></th>
<th><p>To Table: TrvExchSetup</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_AdvAccount</p></td>
<td><p>AdvanceAccountLedgerDimension</p></td>
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
<th><p>From Table: TrvPartyEmployeeRelationship</p></th>
<th><p>To Table: TrvPartyEmployeeRelationship</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_AccountNumber</p></td>
<td><p>LedgerDimension</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

