---
title: ReleaseUpdateDB60_Ledger.allowDupCustomsInvRegJourTable_IN
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupCustomsInvRegJourTable_IN
ms:assetid: fa357cbf-f6a3-acf8-a169-c33c97c43253
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720055(v=AX.60)
ms:contentKeyID: 49712361
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupCustomsInvRegJourTable\_IN 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowDupCustomsInvRegJourTable_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the OrderIdInvoiceRegnIdx index in the CustomsInvoiceRegnJournalTable_IN table to allow for duplicate records.</p></td>
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
<td><p>Ledger</p></td>
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
<td><p>CustomsInvoiceRegnJournalTable_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The ImporterInvoiceNumber field is replaced with the new CustomsImportInvoiceNumberTable surrogate key field in the OrderIdInvoiceRegnIdx unique index. Initially the CustomsImportInvoiceNumberTable field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields in the CustomsImportInvoiceNumberTable\_IN table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

