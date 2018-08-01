---
title: ReleaseUpdateDB60_Ledger.allowDupCustImportInvVendAcctSetup_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupCustImportInvVendAcctSetup_IN Upgrade Script
ms:assetid: 1748ea6c-f749-16fb-bfbf-016a3989c18d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718576(v=AX.60)
ms:contentKeyID: 49706860
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupCustImportInvVendAcctSetup\_IN Upgrade Script 


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
<td><p>Updates the AccountNumIdx index in the CustomsComponentTaxCodes_IN table to allow duplicate records.</p></td>
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

The ImportInvoiceNumber field is replaced with the new CustomsImportInvoiceNumberTable surrogate key field in the unique AccountNumIdx index. Initially the CustomsImportInvoiceNumberTable field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields of the CustomsImportInvoiceVendAcctSetup\_IN table.

  


