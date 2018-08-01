---
title: ReleaseUpdateDB60_PSA.updatePSAProjRevenueTrans Upgrade Script
TOCTitle: ReleaseUpdateDB60_PSA.updatePSAProjRevenueTrans Upgrade Script
ms:assetid: 392afe0d-6df6-7b2e-add4-6671a54381c5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685227(v=AX.60)
ms:contentKeyID: 49707679
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_PSA.updatePSAProjRevenueTrans Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_PSA</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePSAProjRevenueTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the PSAProjRevenueTrans table for up taking the split billing rule by using the new funding source functionality.</p></td>
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
<td><p>Project</p></td>
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
<td><p>DEL_EmplTable</p></td>
</tr>
<tr class="even">
<td><p>DEL_PSAProjRevenueTrans</p></td>
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
<td><p>HcmWorker</p></td>
</tr>
<tr class="even">
<td><p>LedgerParameters</p></td>
</tr>
<tr class="odd">
<td><p>MainAccount</p></td>
</tr>
<tr class="even">
<td><p>ProjProposalJour</p></td>
</tr>
<tr class="odd">
<td><p>ProjRevenueTransSale</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

