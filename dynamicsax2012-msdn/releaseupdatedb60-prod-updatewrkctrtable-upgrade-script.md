---
title: ReleaseUpdateDB60_Prod.updateWrkCtrTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Prod.updateWrkCtrTable Upgrade Script
ms:assetid: f640ba13-884f-bf46-654d-327190ed0988
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737561(v=AX.60)
ms:contentKeyID: 49712255
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Prod.updateWrkCtrTable Upgrade Script 


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
<td><p>updateWrkCtrTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the AccountNumber and Dimension fields to the LedgerDimension and DefaultDimension fields, respectively, in the WrkCtrTable table.</p></td>
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
<td><p>WrkCtrTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WrkCtrTable</p></th>
<th><p>To Table: WrkCtrTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AccountWIPIssue</p></td>
<td><p>WIPIssueLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>AccountWIPValuation</p></td>
<td><p>WIPValuationLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>AccountWrkCtrIssueOffset</p></td>
<td><p>ResourceIssueOffsetLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>AccountWrkCtrIssue</p></td>
<td><p>ResourceIssueLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>Dimension</p></td>
<td><p>DefaultDimension</p></td>
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
<td><p>WrkCtrTable</p></td>
<td><p>WIPIssueLedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrTable</p></td>
<td><p>WIPValuationLedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrTable</p></td>
<td><p>ResourceIssueOffsetLedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrTable</p></td>
<td><p>ResourceIssueLedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrTable</p></td>
<td><p>DefaultDimension</p></td>
<td><p>DimensionDefault</p></td>
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
<td><p>WrkCtrTable</p></td>
<td><p>AccountWIPIssue</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrTable</p></td>
<td><p>AccountWIPValuation</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrTable</p></td>
<td><p>AccountWrkCtrIssueOffset</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrTable</p></td>
<td><p>AccountWrkCtrIssue</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrTable</p></td>
<td><p>Dimension</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

