---
title: ReleaseUpdateTransformDB40_Ledger.ledgerChartOfAccountsPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Ledger.ledgerChartOfAccountsPreProcessing Upgrade Script
ms:assetid: 002bab5a-f501-e57e-1720-39d679509b91
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684601(v=AX.60)
ms:contentKeyID: 49706300
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Ledger.ledgerChartOfAccountsPreProcessing Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>ledgerChartOfAccountsPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates a LedgerChartOfAccountsUpg record for each company.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p>
<p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>LedgerChartOfAccountsUpg</p></td>
</tr>
<tr class="even">
<td><p>LedgerChartOfAccountsStructure</p></td>
</tr>
</tbody>
</table>


## Remarks

The LedgerChartOfAccountsUpg table data will be imported into the LedgerChartOfAccounts table during the bulk copy process. This upgrade is required in order to convert account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CompanyInfo</p></th>
<th><p>To Table: LedgerChartOfAccountsUpg</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DataAreaId</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p>Name</p></td>
<td><p>Description</p></td>
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
<th><p>From Table: LedgerChartOfAccountsUpg</p></th>
<th><p>To Table: LedgerChartOfAccountsStructure</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>ChartOfAccounts</p></td>
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
<th><p>From Table: DimensionHierarchy</p></th>
<th><p>To Table: LedgerChartOfAccountsStructure</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>DimensionHierarchy</p></td>
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
<td><p>LedgerChartOfAccountsUpg</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>LedgerChartOfAccountsStructure</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

