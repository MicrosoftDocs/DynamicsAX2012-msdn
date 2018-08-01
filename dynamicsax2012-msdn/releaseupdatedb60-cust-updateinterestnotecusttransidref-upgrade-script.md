---
title: ReleaseUpdateDB60_Cust.updateInterestNoteCustTransIdRef Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateInterestNoteCustTransIdRef Upgrade Script
ms:assetid: 0dc0c3d8-cddb-ed3d-6ed8-2fab6e6c44f0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735720(v=AX.60)
ms:contentKeyID: 49706625
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateInterestNoteCustTransIdRef Upgrade Script 


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
<td><p>updateInterestNoteCustTransIdRef</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the CustTransIdRef table with the reference of fee vouchers and transaction vouchers that are associated with the interest note.</p></td>
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
<td><p>CustTransIdRef</p></td>
</tr>
<tr class="even">
<td><p>CustTrans</p></td>
</tr>
<tr class="odd">
<td><p>CustInterestJour</p></td>
</tr>
<tr class="even">
<td><p>CustInterestTrans</p></td>
</tr>
<tr class="odd">
<td><p>CustCollectionLetterJour</p></td>
</tr>
<tr class="even">
<td><p>GeneralJournalEntry</p></td>
</tr>
</tbody>
</table>


## Remarks

In previous versions, the fee and transaction vouchers used to have one voucher per interest note. In the current release, fee and transaction vouchers are posted in separate vouchers. The CustTransIdRef table stores the references that are associated with the voucher that is related to the customer transactions. This method will update the voucher references in the CustTransIdRef table for the interest note.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CustTrans</p></th>
<th><p>To Table: CustTransIdRef</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>TransRecId</p></td>
</tr>
<tr class="even">
<td><p>custTransRefType</p></td>
<td><p>TransRefType</p></td>
</tr>
</tbody>
</table>

  


