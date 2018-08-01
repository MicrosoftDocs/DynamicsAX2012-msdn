---
title: ReleaseUpdateDB60_Prod.updateProdGroup Upgrade Script
TOCTitle: ReleaseUpdateDB60_Prod.updateProdGroup Upgrade Script
ms:assetid: 795890fb-1bd9-8275-a029-4c08f23bbdb6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719393(v=AX.60)
ms:contentKeyID: 49709184
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Prod.updateProdGroup Upgrade Script 


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
<td><p>updateProdGroup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates all the fields of type LedgerDimensionDefaultAccount of the ProdGroup table with the corresponding value from the RecId field of the DimensionAttributeValueCombination table.</p></td>
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
<td><p>ProdGroup</p></td>
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
<td><p>ProdGroup</p></td>
<td><p>IssueLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>ProdGroup</p></td>
<td><p>IssueOffsetLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>ProdGroup</p></td>
<td><p>PickListLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>ProdGroup</p></td>
<td><p>PickListOffsetLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>ProdGroup</p></td>
<td><p>ReceiptLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>ProdGroup</p></td>
<td><p>ReceiptOffsetLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>ProdGroup</p></td>
<td><p>ReportLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>ProdGroup</p></td>
<td><p>ReportOffsetLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>ProdGroup</p></td>
<td><p>WIPIssueLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>ProdGroup</p></td>
<td><p>WIPValuationLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>ProdGroup</p></td>
<td><p>ResourceIssueLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>ProdGroup</p></td>
<td><p>ResourceIssueOffsetLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
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
<td><p>ProdGroup</p></td>
<td><p>AccountIssue</p></td>
</tr>
<tr class="even">
<td><p>ProdGroup</p></td>
<td><p>AccountIssueOffset</p></td>
</tr>
<tr class="odd">
<td><p>ProdGroup</p></td>
<td><p>AccountPickList</p></td>
</tr>
<tr class="even">
<td><p>ProdGroup</p></td>
<td><p>AccountPicklistOffset</p></td>
</tr>
<tr class="odd">
<td><p>ProdGroup</p></td>
<td><p>AccountReceipt</p></td>
</tr>
<tr class="even">
<td><p>ProdGroup</p></td>
<td><p>AccountReceiptOffset</p></td>
</tr>
<tr class="odd">
<td><p>ProdGroup</p></td>
<td><p>AccountReportFinished</p></td>
</tr>
<tr class="even">
<td><p>ProdGroup</p></td>
<td><p>AccountReportFinishedOffset</p></td>
</tr>
<tr class="odd">
<td><p>ProdGroup</p></td>
<td><p>AccountWIPIssue</p></td>
</tr>
<tr class="even">
<td><p>ProdGroup</p></td>
<td><p>AccountWIPValuation</p></td>
</tr>
<tr class="odd">
<td><p>ProdGroup</p></td>
<td><p>AccountWrkCtrIssue</p></td>
</tr>
<tr class="even">
<td><p>ProdGroup</p></td>
<td><p>AccountWrkCtrIssueOffset</p></td>
</tr>
</tbody>
</table>

  


