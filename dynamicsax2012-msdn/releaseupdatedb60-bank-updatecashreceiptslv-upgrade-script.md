---
title: ReleaseUpdateDB60_Bank.UpdateCashReceiptsLV Upgrade Script
TOCTitle: ReleaseUpdateDB60_Bank.UpdateCashReceiptsLV Upgrade Script
ms:assetid: d8937fee-8ff6-f110-6c79-2d31fcf13cba
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687098(v=AX.60)
ms:contentKeyID: 49711546
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Bank.UpdateCashReceiptsLV Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>UpdateCashReceiptsLV</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the script for the cash receipts table and related fields for Latvia.</p></td>
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
<td><p>LedgerJournalTrans_Rcash</p></td>
</tr>
<tr class="even">
<td><p>RCashTrans</p></td>
</tr>
<tr class="odd">
<td><p>LvCashReceiptTrans</p></td>
</tr>
<tr class="even">
<td><p>LvCashReceiptTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The upgrade script is necessary due to the following changes in the data model from previous version. 1.The FK constraint has been changed from the BatchId field to the RefRecId field. 2. The LV specific fields have been moved from the ledgerJournalTrans table to the LedgerJournalTrans\_RCash table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LvCashReceiptTable</p></th>
<th><p>To Table: LedgerJournalTrans_RCash</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>LvCashReceiptTable</p></td>
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
<th><p>From Table: LvCashReceiptTable</p></th>
<th><p>To Table: RCashTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>LvCashReceiptTable</p></td>
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
<th><p>From Table: LvCashReceiptTable</p></th>
<th><p>To Table: LvCashReceiptTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Recid</p></td>
<td><p>LvCashReceiptTable</p></td>
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
<th><p>From Table: HcmWorker</p></th>
<th><p>To Table: LvCashReceiptTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>HcmWorker</p></td>
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
<td><p>LvCashReceiptTrans</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>LvCashReceiptTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

