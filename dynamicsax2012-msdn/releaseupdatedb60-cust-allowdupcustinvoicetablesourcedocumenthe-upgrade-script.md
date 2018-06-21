---
title: ReleaseUpdateDB60_Cust.allowDupCustInvoiceTableSourceDocumentHe Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.allowDupCustInvoiceTableSourceDocumentHe Upgrade Script
ms:assetid: 4c855fa5-44ec-8e1c-494e-6e3b142e18e8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685412(v=AX.60)
ms:contentKeyID: 49708117
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.allowDupCustInvoiceTableSourceDocumentHe Upgrade Script [AX 2012]


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
<td><p>allowDupCustInvoiceTableSourceDocumentHe</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the SourceDocumentHeaderIdx index in the CustInvoiceTable table to allow for duplicate records.</p></td>
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
<td><p>CustInvoiceTable</p></td>
</tr>
</tbody>
</table>


## Remarks

Disables the unique index for the SourceDocumentHeader field until it can be populated.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

