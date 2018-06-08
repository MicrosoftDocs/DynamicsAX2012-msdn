---
title: ReleaseUpdateDB60_Ledger.allowDupCustImportInvVendAcctSetup_IN
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupCustImportInvVendAcctSetup_IN
ms:assetid: 589bb14f-a3d0-1b6a-014e-b2db121777a3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736241(v=AX.60)
ms:contentKeyID: 49708416
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupCustImportInvVendAcctSetup\_IN 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>allowDupCustImportInvVendAcctSetup_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;AccountNumIdx&lt;/c&gt; in the table &lt;c&gt;CustomsComponentTaxCodes_IN&lt;/c&gt; to allow duplicate records.</p></td>
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
<td><p>CUSTOMSIMPORTINVOICEVENDACCTSETUP_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The ImportInvoiceNumber field is replaced with the new surrogate key field CustomsImportInvoiceNumberTable in the unique index AccountNumIdx. Initially the CustomsImportInvoiceNumberTable field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields of the table CustomsImportInvoiceVendAcctSetup\_IN.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

