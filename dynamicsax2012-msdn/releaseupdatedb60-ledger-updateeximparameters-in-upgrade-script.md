---
title: ReleaseUpdateDB60_Ledger.updateEximParameters_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateEximParameters_IN Upgrade Script
ms:assetid: ade61cae-a109-8469-f2f2-9dc18eb1c8fb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686542(v=AX.60)
ms:contentKeyID: 49710497
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateEximParameters\_IN Upgrade Script 


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
<td><p>updateEximParameters_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the EximParameters_IN table. The values of the RecId field of the DimensionAttributeValueCombination table are now stored in place of the DEL_AABenefitAccount, DEL_DBKBenefitAccount, DEL_DBKReceivableAccount, DEL_DEPBBenefitAccount, and DEL_DFIABenefitAccount values.</p></td>
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
<td><p>EximParameters_IN</p></td>
</tr>
<tr class="even">
<td><p>FinancialTagCategory</p></td>
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
<th><p>From Table: DimensionAttributeValueCombination</p></th>
<th><p>To Table: eximParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>AABenefitLedgerDimension</p></td>
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
<th><p>From Table: DimensionAttributeValueCombination</p></th>
<th><p>To Table: eximParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>DBKBenefitLedgerDimension</p></td>
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
<th><p>From Table: DimensionAttributeValueCombination</p></th>
<th><p>To Table: eximParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>DBKReceivableLedgerDimension</p></td>
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
<th><p>From Table: DimensionAttributeValueCombination</p></th>
<th><p>To Table: eximParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>DEPBBenefitLedgerDimension</p></td>
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
<th><p>From Table: DimensionAttributeValueCombination</p></th>
<th><p>To Table: eximParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>DFIABenefitLedgerDimension</p></td>
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
<td><p>eximParameters</p></td>
<td><p>AABenefitLedgerDimension</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>eximParameters</p></td>
<td><p>DBKBenefitLedgerDimension</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>eximParameters</p></td>
<td><p>DBKReceivableLedgerDimension</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>eximParameters</p></td>
<td><p>DEPBBenefitLedgerDimension</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>eximParameters</p></td>
<td><p>DFIABenefitLedgerDimension</p></td>
<td><p>RefRecId</p></td>
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
<td><p>eximParameters</p></td>
<td><p>DEL_AABenefitAccount</p></td>
</tr>
<tr class="even">
<td><p>eximParameters</p></td>
<td><p>DEL_DBKBenefitAccount</p></td>
</tr>
<tr class="odd">
<td><p>eximParameters</p></td>
<td><p>DEL_DBKReceivableAccount</p></td>
</tr>
<tr class="even">
<td><p>eximParameters</p></td>
<td><p>DEL_DEPBBenefitAccount</p></td>
</tr>
<tr class="odd">
<td><p>eximParameters</p></td>
<td><p>DEL_DFIABenefitAccount</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

