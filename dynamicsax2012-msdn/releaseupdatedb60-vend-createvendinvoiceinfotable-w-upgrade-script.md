---
title: ReleaseUpdateDB60_Vend.createVendInvoiceInfoTable_W Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.createVendInvoiceInfoTable_W Upgrade Script
ms:assetid: 395d4c67-657a-b1ac-dbb0-1f3b3a11b68d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685233(v=AX.60)
ms:contentKeyID: 49707685
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.createVendInvoiceInfoTable\_W Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>createVendInvoiceInfoTable_W</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates country specific fields from &lt;c&gt;VendInvoiceInfoTable&lt;/c&gt; table to &lt;c&gt;VendInvoiceInfoTable_W&lt;/c&gt; table</p></td>
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
<td><p>VendInvoiceInfoTable</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceInfoTable_W</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: VendInvoiceInfoTable</p></th>
<th><p>To Table: VendInvoiceInfoTable_W</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Authority_BR</p></td>
<td><p>Authority_BR</p></td>
</tr>
<tr class="even">
<td><p>ConsignmentNoteNum_IN</p></td>
<td><p>ConsignmentNoteNum_IN</p></td>
</tr>
<tr class="odd">
<td><p>ConsTarget_JP</p></td>
<td><p>ConsTarget_JP</p></td>
</tr>
<tr class="even">
<td><p>CustomsBillOfEntryNumberTable_IN</p></td>
<td><p>CustomsBillOfEntryNumberTable_IN</p></td>
</tr>
<tr class="odd">
<td><p>CustomsImportInvoiceNumberTable_IN</p></td>
<td><p>CustomsImportInvoiceNumberTable_IN</p></td>
</tr>
<tr class="even">
<td><p>DocRegister_LT</p></td>
<td><p>DocRegister_LT</p></td>
</tr>
<tr class="odd">
<td><p>ElectronicInvoice_BR</p></td>
<td><p>ElectronicInvoice_BR</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentModel_BR</p></td>
<td><p>FiscalDocumentModel_BR</p></td>
</tr>
<tr class="odd">
<td><p>FiscalDocumentSeries_BR</p></td>
<td><p>FiscalDocumentSeries_BR</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentSpecie_BR</p></td>
<td><p>FiscalDocumentSpecie_BR</p></td>
</tr>
<tr class="odd">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>FiscalDocumentType_BR</p></td>
</tr>
<tr class="even">
<td><p>PackingSlipIdForUpdate_W</p></td>
<td><p>PackingSlipIdForUpdate_W</p></td>
</tr>
<tr class="odd">
<td><p>PurchReceiptDate_W</p></td>
<td><p>PurchReceiptDate_W</p></td>
</tr>
<tr class="even">
<td><p>RefProcessNo_BR</p></td>
<td><p>RefProcessNo_BR</p></td>
</tr>
<tr class="odd">
<td><p>ServiceCodeOnDlvAddress_BR</p></td>
<td><p>ServiceCodeOnDlvAddress_BR</p></td>
</tr>
<tr class="even">
<td><p>TaxInformation_IN</p></td>
<td><p>TaxInformation_IN</p></td>
</tr>
<tr class="odd">
<td><p>TaxPeriodPaymentCode_PL</p></td>
<td><p>TaxPeriodPaymentCode_PL</p></td>
</tr>
<tr class="even">
<td><p>VatDueDate_W</p></td>
<td><p>VatDueDate_W</p></td>
</tr>
<tr class="odd">
<td><p>VendFinalUser_BR</p></td>
<td><p>VendFinalUser_BR</p></td>
</tr>
<tr class="even">
<td><p>EmplAccount_RU</p></td>
<td><p>EmplAccount_RU</p></td>
</tr>
<tr class="odd">
<td><p>UseStateInvoice_LV</p></td>
<td><p>UseStateInvoice_LV</p></td>
</tr>
</tbody>
</table>

  


