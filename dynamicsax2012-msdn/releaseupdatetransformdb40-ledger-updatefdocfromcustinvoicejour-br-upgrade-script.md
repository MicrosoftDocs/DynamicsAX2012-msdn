﻿---
title: ReleaseUpdateTransformDB40_Ledger.updateFDocFromCustInvoiceJour_BR Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Ledger.updateFDocFromCustInvoiceJour_BR Upgrade Script
ms:assetid: 251a6c42-45d1-2fdf-d837-6102441cdcca
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685018(v=AX.60)
ms:contentKeyID: 49707218
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Ledger.updateFDocFromCustInvoiceJour\_BR Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateFDocFromCustInvoiceJour_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This script is used for updating the fiscal document related to customer invoices.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p>
<p>Pre-processing60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>FiscalDocument_BR</p></td>
</tr>
<tr class="even">
<td><p>LogisticsPostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>DEL_CustInvoiceJourUpgrade_BR</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentLine_BR</p></td>
</tr>
<tr class="odd">
<td><p>FiscalDocumentCustVendTrans_BR</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentInstallment_BR</p></td>
</tr>
<tr class="odd">
<td><p>FiscalDocumentReferencedProcess_BR</p></td>
</tr>
<tr class="even">
<td><p>FisalDocumentShipmentStat_BR</p></td>
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
<th><p>From Table: CustInvoiceJour</p></th>
<th><p>To Table: FiscalDocument_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>TableId</p></td>
<td><p>RefTableId</p></td>
</tr>
<tr class="odd">
<td><p>Status_BR</p></td>
<td><p>Status</p></td>
</tr>
<tr class="even">
<td><p>InvoiceDate</p></td>
<td><p>FiscalDocumentDate</p></td>
</tr>
<tr class="odd">
<td><p>InvoiceDate</p></td>
<td><p>AccountingDate</p></td>
</tr>
<tr class="even">
<td><p>InvoiceNumber</p></td>
<td><p>FiscalDocumentNumber</p></td>
</tr>
<tr class="odd">
<td><p>InvoiceSeries</p></td>
<td><p>FiscalDocumentSeries</p></td>
</tr>
<tr class="even">
<td><p>InvoiceModel_BR</p></td>
<td><p>Model</p></td>
</tr>
<tr class="odd">
<td><p>LedgerVoucher</p></td>
<td><p>Voucher</p></td>
</tr>
<tr class="even">
<td><p>InvoiceAccount</p></td>
<td><p>FiscalDocumentAccountNum</p></td>
</tr>
<tr class="odd">
<td><p>InvoiceAmountMST</p></td>
<td><p>TotalAmount</p></td>
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
<th><p>From Table: CompanyInfo</p></th>
<th><p>To Table: FiscalDocument_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>FiscalEstablishmentName</p></td>
</tr>
<tr class="even">
<td><p>CNPJCPFNum</p></td>
<td><p>FiscalEstablishmentCNPJCPF</p></td>
</tr>
<tr class="odd">
<td><p>CCMNum</p></td>
<td><p>FiscalEstablishmentCCMNum</p></td>
</tr>
<tr class="even">
<td><p>IEnum</p></td>
<td><p>FiscalEstablishmentIE</p></td>
</tr>
<tr class="odd">
<td><p>Phone</p></td>
<td><p>FiscalEstablishmentPhone</p></td>
</tr>
<tr class="even">
<td><p>TributarySubstitutionRegistry</p></td>
<td><p>FiscalEstablishmentTribSubstitutionReg</p></td>
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
<th><p>From Table: CustTable</p></th>
<th><p>To Table: FiscalDocument_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>ThirdPartyName</p></td>
</tr>
<tr class="even">
<td><p>CNPJCPFNum</p></td>
<td><p>ThirdPartyCNPJCPF</p></td>
</tr>
<tr class="odd">
<td><p>CCMNum</p></td>
<td><p>ThirdPartyCCMNum</p></td>
</tr>
<tr class="even">
<td><p>IENum</p></td>
<td><p>ThirdPartyIE</p></td>
</tr>
<tr class="odd">
<td><p>Phone</p></td>
<td><p>ThirdPartyPhone</p></td>
</tr>
<tr class="even">
<td><p>TeleFax</p></td>
<td><p>ThirdPartyFax</p></td>
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
<th><p>From Table: CustInvoiceJour</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>InvoicingName</p></td>
<td><p>Address</p></td>
</tr>
<tr class="even">
<td><p>InvCountryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>InvState</p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p>InvZipCode</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="odd">
<td><p>InvoiceCity</p></td>
<td><p>City</p></td>
</tr>
<tr class="even">
<td><p>InvoiceStreet</p></td>
<td><p>Street</p></td>
</tr>
<tr class="odd">
<td><p>InvAddressNumber</p></td>
<td><p>StreetNumber</p></td>
</tr>
<tr class="even">
<td><p>InvDistrictName</p></td>
<td><p>DistrictName</p></td>
</tr>
<tr class="odd">
<td><p>InvAddressComplement</p></td>
<td><p>BuildingCompliment</p></td>
</tr>
<tr class="even">
<td><p>DeliveryAddress</p></td>
<td><p>Address</p></td>
</tr>
<tr class="odd">
<td><p>DlvCountryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="even">
<td><p>DlvState</p></td>
<td><p>State</p></td>
</tr>
<tr class="odd">
<td><p>DlvZipCode</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="even">
<td><p>DeliveryCity</p></td>
<td><p>City</p></td>
</tr>
<tr class="odd">
<td><p>DeliveryStreet</p></td>
<td><p>Street</p></td>
</tr>
<tr class="even">
<td><p>DlvAddressNumber</p></td>
<td><p>StreetNumber</p></td>
</tr>
<tr class="odd">
<td><p>DlvDistrictName</p></td>
<td><p>DistrictName</p></td>
</tr>
<tr class="even">
<td><p>DlvAddressComplement</p></td>
<td><p>BuildingCompliment</p></td>
</tr>
<tr class="odd">
<td><p>DlvTransportBrand</p></td>
<td><p>PackingBrand</p></td>
</tr>
<tr class="even">
<td><p>DlvNoOfCarrier</p></td>
<td><p>VehicleLicensePlateNumber</p></td>
</tr>
<tr class="odd">
<td><p>DlvMode</p></td>
<td><p>DeliveryMode</p></td>
</tr>
<tr class="even">
<td><p>DlvTerm</p></td>
<td><p>DeliveryTerm</p></td>
</tr>
<tr class="odd">
<td><p>InvoiceComplementaryType</p></td>
<td><p>ComplementaryType</p></td>
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
<th><p>From Table: SalesCarrier</p></th>
<th><p>To Table: FiscalDocument_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>SalesCarrier</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
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
<th><p>From Table: LogisticsPostalAddress</p></th>
<th><p>To Table: FiscalDocument_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>SalesCarrierLogisticsPostalAddress</p></td>
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
<th><p>From Table: FiscalDocument_BR</p></th>
<th><p>To Table: FiscalDocumentLine_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>FiscalDocument</p></td>
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
<th><p>From Table: CustInvoiceTrans</p></th>
<th><p>To Table: FiscalDocumentLine_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TableId</p></td>
<td><p>RefTableId</p></td>
</tr>
<tr class="even">
<td><p>RecId</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>LineNum</p></td>
<td><p>LineNum</p></td>
</tr>
<tr class="even">
<td><p>ItemId</p></td>
<td><p>ItemId</p></td>
</tr>
<tr class="odd">
<td><p>CustCFOPId</p></td>
<td><p>CFOP</p></td>
</tr>
<tr class="even">
<td><p>Name</p></td>
<td><p>Description</p></td>
</tr>
<tr class="odd">
<td><p>TaxFiscalClassificationId</p></td>
<td><p>FiscalClassification</p></td>
</tr>
<tr class="even">
<td><p>ExceptionCode_BR</p></td>
<td><p>ExceptionCode</p></td>
</tr>
<tr class="odd">
<td><p>TaxationOrigin</p></td>
<td><p>Origin</p></td>
</tr>
<tr class="even">
<td><p>InventTransId</p></td>
<td><p>InventTransId</p></td>
</tr>
<tr class="odd">
<td><p>SalesUnit</p></td>
<td><p>Unit</p></td>
</tr>
<tr class="even">
<td><p>Qty</p></td>
<td><p>Quantity</p></td>
</tr>
<tr class="odd">
<td><p>ServiceCodeId</p></td>
<td><p>ServiceCode</p></td>
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
<th><p>From Table: FiscalDocument_BR</p></th>
<th><p>To Table: FiscalDocumentCustVendTrans_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>FiscalDocument</p></td>
</tr>
<tr class="even">
<td><p>TotalAmount</p></td>
<td><p>Amount</p></td>
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
<th><p>From Table: CustInvoiceJour</p></th>
<th><p>To Table: FiscalDocumentCustVendTrans_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PrimaryMethod_BR</p></td>
<td><p>PrimaryMethod</p></td>
</tr>
<tr class="even">
<td><p>DueDate</p></td>
<td><p>DueDate</p></td>
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
<th><p>From Table: FiscalDocumentCustVendTrans_BR</p></th>
<th><p>To Table: FiscalDocumentInstallment_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>FiscalDocumentCustVendTrans</p></td>
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
<th><p>From Table: CustPaymSchedLine</p></th>
<th><p>To Table: FiscalDocumentInstallment_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DueAmount</p></td>
<td><p>Amount</p></td>
</tr>
<tr class="even">
<td><p>DueDate</p></td>
<td><p>DueDate</p></td>
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
<th><p>From Table: FiscalDocument_BR</p></th>
<th><p>To Table: FiscalDocumentReferencedProcess_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Recid</p></td>
<td><p>FiscalDocument</p></td>
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
<th><p>From Table: CustInvoiceJour</p></th>
<th><p>To Table: FiscalDocumentReferencedProcess_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Agency_BR</p></td>
<td><p>Agency</p></td>
</tr>
<tr class="even">
<td><p>RefProcessNo_BR</p></td>
<td><p>ProcessNumber</p></td>
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
<th><p>From Table: FiscalDocument_BR</p></th>
<th><p>To Table: FiscalDocumentShipmentStat_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>FiscalDocument</p></td>
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
<th><p>From Table: SalesShipmentStat</p></th>
<th><p>To Table: FiscalDocumentShipmentStat_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>GrossWeight</p></td>
<td><p>GrossWeight</p></td>
</tr>
<tr class="even">
<td><p>NetWeight</p></td>
<td><p>NetWeight</p></td>
</tr>
<tr class="odd">
<td><p>VolumeType_BR</p></td>
<td><p>VolumeType</p></td>
</tr>
<tr class="even">
<td><p>VolumeQty_BR</p></td>
<td><p>VolumeQuantity</p></td>
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
<td><p>FiscalDocument_BR</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentLine_BR</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>FiscalDocumentCustVendTrans_BR</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentInstallment_BR</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>FiscalDocumentReferencedProcess_BR</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentShipmentStat_BR</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

