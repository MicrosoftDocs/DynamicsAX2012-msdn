---
title: ReleaseUpdateDB60_Vend.updateCashDisc Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateCashDisc Upgrade Script
ms:assetid: 087e7e65-a8c7-e372-ac25-e5d4a6eca49e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684786(v=AX.60)
ms:contentKeyID: 49706479
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateCashDisc Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCashDisc</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the AccountPaid and AccountReceived fields to the PaidLedgerDimension and ReceivedLedgerDimension fields, respectively, in the CashDisc table.</p></td>
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
<td><p>Accounts payable</p></td>
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
<td><p>CashDisc</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert the account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CashDisc</p></th>
<th><p>To Table: CashDisc</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AccountPaid</p></td>
<td><p>PaidLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>AccountReceived</p></td>
<td><p>ReceivedLedgerDimension</p></td>
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
<td><p>CashDisc</p></td>
<td><p>PaidLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>CashDisc</p></td>
<td><p>ReceivedLedgerDimension</p></td>
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
<td><p>CashDisc</p></td>
<td><p>AccountPaid</p></td>
</tr>
<tr class="even">
<td><p>CashDisc</p></td>
<td><p>AccountReceived</p></td>
</tr>
</tbody>
</table>

  


