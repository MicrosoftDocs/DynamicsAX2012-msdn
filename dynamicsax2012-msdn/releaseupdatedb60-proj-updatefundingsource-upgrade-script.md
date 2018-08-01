---
title: ReleaseUpdateDB60_Proj.updateFundingSource Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateFundingSource Upgrade Script
ms:assetid: f9bf11b5-a072-a9cb-84d4-c55c3dd95ed2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720075(v=AX.60)
ms:contentKeyID: 49712381
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateFundingSource Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Proj</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateFundingSource</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates a record for each contract, which represents the funding entity. Funding entities are the revenue streams for a contract. Revenue streams may be of type Customer, Grant, or Organizational Unit.</p></td>
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
<td><p>ProjFundingSource</p></td>
</tr>
</tbody>
</table>


## Remarks

One record will be created for each contract. The record will contain a reference to the contract and invoice account and the FundingType field set to the ProjFundingType::Customer enumeration value.

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
<td><p>ProjFundingSource</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


