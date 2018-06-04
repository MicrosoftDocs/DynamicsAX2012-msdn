---
title: ReleaseUpdateDB60_Cust.updateCustIntTransLedgerEntRef Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCustIntTransLedgerEntRef Upgrade Script
ms:assetid: ad62284b-9173-600f-5250-1a99dffe50e3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686517(v=AX.60)
ms:contentKeyID: 49710472
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCustIntTransLedgerEntRef Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCustIntTransLedgerEntRef</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the CustInterestTrans.LedgerEntryReference field by matching the CustInterestJour.LedgerVoucher field with the LedgerEntryReference.ReferenceNumber field.</p></td>
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
<td><p>Accounts receivable</p></td>
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
<td><p>CustInterestTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

The LedgerVoucher field of the CustInterestJour table will now be storing only Fee vouchers and not the transaction voucher. To upgrade the old data, this method will copy Fee voucher data to the vouchers of interest note transactions.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CustInterestJour</p></th>
<th><p>To Table: CustInterestTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>FeeVoucher</p></td>
<td><p>LedgerEntryReference</p></td>
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
<td><p>CustInterestTrans</p></td>
<td><p>LedgerEntryReference</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Name Changes for Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Old Table Name:</p></th>
<th><p>New Table Name:</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>CustInterestJour.LedgerVoucher</p></td>
<td><p>CustInterestJour.FeeVoucher</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

