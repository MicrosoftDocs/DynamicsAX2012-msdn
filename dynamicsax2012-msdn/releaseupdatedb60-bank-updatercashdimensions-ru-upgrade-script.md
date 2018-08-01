---
title: ReleaseUpdateDB60_Bank.updateRCashDimensions_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Bank.updateRCashDimensions_RU Upgrade Script
ms:assetid: 93228936-440f-a67d-62a7-1ee79c328e29
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686113(v=AX.60)
ms:contentKeyID: 49709817
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Bank.updateRCashDimensions\_RU Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Bank</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateRCashDimensions_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the SumAccount field to the SumLedgerDimension field in the RCashLedgerAccount table, also transforms the RCashParameters fields.</p></td>
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
<td><p>Bank</p></td>
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
<td><p>RCashLedgerAccount</p></td>
</tr>
<tr class="even">
<td><p>RCashParameters</p></td>
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
<th><p>From Table: RCashLedgerAccount</p></th>
<th><p>To Table: RCashLedgerAccount</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SumLedgerDimension</p></td>
<td><p>SumAccount</p></td>
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
<th><p>From Table: RCashParameters</p></th>
<th><p>To Table: RCashParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PurposeCode</p></td>
<td><p>PurposeDimensionAttribute</p></td>
</tr>
<tr class="even">
<td><p>AnalysisCode</p></td>
<td><p>AnalysisDimensionAttribute</p></td>
</tr>
<tr class="odd">
<td><p>DepartmentCode</p></td>
<td><p>DepartmentDimensionAttribute</p></td>
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
<td><p>RCashLedgerAccount</p></td>
<td><p>SumLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>RCashParameters</p></td>
<td><p>PurposeDimensionAttribute</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>RCashParameters</p></td>
<td><p>AnalysisDimensionAttribute</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>RCashParameters</p></td>
<td><p>DepartmentDimensionAttribute</p></td>
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
<td><p>RCashLedgerAccount</p></td>
<td><p>SumAccount</p></td>
</tr>
<tr class="even">
<td><p>RCashParameters</p></td>
<td><p>PurposeCode</p></td>
</tr>
<tr class="odd">
<td><p>RCashParameters</p></td>
<td><p>AnalysisCode</p></td>
</tr>
<tr class="even">
<td><p>RCashParameters</p></td>
<td><p>DepartmentCode</p></td>
</tr>
</tbody>
</table>

  


