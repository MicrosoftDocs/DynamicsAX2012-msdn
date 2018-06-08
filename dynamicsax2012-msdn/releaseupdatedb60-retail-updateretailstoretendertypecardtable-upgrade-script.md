---
title: ReleaseUpdateDB60_Retail.updateRetailStoreTenderTypeCardTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Retail.updateRetailStoreTenderTypeCardTable Upgrade Script
ms:assetid: 8d57e6bc-db25-d203-a9b2-2a610c728eca
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736478(v=AX.60)
ms:contentKeyID: 49709666
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.updateRetailStoreTenderTypeCardTable Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Retail</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateRetailStoreTenderTypeCardTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the accountRelation field to the LedgerDimension field in the RetailStoreTenderTypeCardTable table. Updates the cardFeeAccount field to the CardFeeLedgerDimension in the RetailStoreTenderTypeCardTable table. Updates the cardFeeOffsetAccount field to the CardFeeOffsetLedgerDimension in the RetailStoreTenderTypeCardTable table. Updates the differenceAccount field to the DifferenceAccLedgerDimension in the RetailStoreTenderTypeCardTable table. Updates the differenceAccountForBigDifference field to the DiffAccBigDiffLedgerDimension field in the RetailStoreTenderTypeCardTable table.</p></td>
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
<td><p>Retail</p></td>
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
<td><p>DIMENSIONATTRIBUTE</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONATTRIBUTEDIRCATEGORY</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONATTRIBUTELEVELVALUE</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONATTRIBUTESET</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONATTRIBUTESETITEM</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONATTRIBUTEVALUE</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONATTRIBUTEVALUECOMBINATION</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONATTRIBUTEVALUECOMBINATIONSTATUS</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONATTRIBUTEVALUEGROUP</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONATTRIBUTEVALUEGROUPCOMBINATION</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONATTRIBUTEVALUEGROUPSTATUS</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONATTRIBUTEVALUESET</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONATTRIBUTEVALUESETITEM</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONFINANCIALTAG</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONHIERARCHY</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONHIERARCHYLEVEL</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONVALUEGROUPJOURNALCONTROLSTATUS</p></td>
</tr>
<tr class="even">
<td><p>FINANCIALTAGCATEGORY</p></td>
</tr>
<tr class="odd">
<td><p>LEDGERPARAMETERS</p></td>
</tr>
<tr class="even">
<td><p>MAINACCOUNT</p></td>
</tr>
<tr class="odd">
<td><p>RETAILSTORETENDERTYPECARDTABLE</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

