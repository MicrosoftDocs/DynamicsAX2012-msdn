---
title: ReleaseUpdateTransformDB50_Ledger.updateFiscalDocumentsDelta_BR Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Ledger.updateFiscalDocumentsDelta_BR Upgrade Script
ms:assetid: 5470dd19-08ea-4dc2-c97a-16af25247fcd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736154(v=AX.60)
ms:contentKeyID: 49708331
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Ledger.updateFiscalDocumentsDelta\_BR Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateFiscalDocumentsDelta_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This script is used for updating the fiscal documents.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p>
<p>Pre-processing60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>DEL_FiscalDocJourUpgrade_BR</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocument_BR</p></td>
</tr>
<tr class="odd">
<td><p>FiscalDocTrans_BR</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentLine_BR</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsPostalAddres</p></td>
</tr>
<tr class="even">
<td><p>DEL_FiscalDocJourUpgrade_BR</p></td>
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
<td><p>FiscalDocumentShipmentStat_BR</p></td>
</tr>
</tbody>
</table>


## Remarks

The script creates the new fiscal document model based on \<c\>FiscalDocJour\</c\> and \<c\>FiscalDocTrans\</c\> tables information.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: FiscalDocJour</p></th>
<th><p>To Table: FiscalDocument_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RefRecId</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>RefTableId</p></td>
<td><p>RefTableId</p></td>
</tr>
<tr class="odd">
<td><p>Status</p></td>
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
<td><p>FiscalDocNumber</p></td>
<td><p>FiscalDocumentNumber</p></td>
</tr>
<tr class="odd">
<td><p>InvoiceSeries</p></td>
<td><p>FiscalDocumentSeries</p></td>
</tr>
<tr class="even">
<td><p>InventoryDirection</p></td>
<td><p>Direction</p></td>
</tr>
<tr class="odd">
<td><p>Voucher</p></td>
<td><p>Voucher</p></td>
</tr>
<tr class="even">
<td><p>CFOPName</p></td>
<td><p>OperationDescription</p></td>
</tr>
<tr class="odd">
<td><p>InvoiceAccount</p></td>
<td><p>FiscalDocumentAccountNum</p></td>
</tr>
<tr class="even">
<td><p>DeliveryCNPJCPFNum</p></td>
<td><p>DeliveryCNPJCPF</p></td>
</tr>
<tr class="odd">
<td><p>DeliveryIENum</p></td>
<td><p>DeliveryIE</p></td>
</tr>
<tr class="even">
<td><p>DeliveryVehicleBrand</p></td>
<td><p>PackingBrand</p></td>
</tr>
<tr class="odd">
<td><p>DeliveryVehicleLicense</p></td>
<td><p>VehicleLicensePlateNumber</p></td>
</tr>
<tr class="even">
<td><p>DeliveryVehicleLicenseState</p></td>
<td><p>VehicleLicensePlateState</p></td>
</tr>
<tr class="odd">
<td><p>ComplementaryInvoice</p></td>
<td><p>ComplementaryInvoice</p></td>
</tr>
<tr class="even">
<td><p>DlvMode</p></td>
<td><p>DeliveryMode</p></td>
</tr>
<tr class="odd">
<td><p>DlvTerm</p></td>
<td><p>DeliveryTerm</p></td>
</tr>
<tr class="even">
<td><p>ComplementaryType</p></td>
<td><p>ComplementaryType</p></td>
</tr>
<tr class="odd">
<td><p>TotalAmount</p></td>
<td><p>TotalAmount</p></td>
</tr>
<tr class="even">
<td><p>TotalGoodsAmount</p></td>
<td><p>TotalGoodsAmount</p></td>
</tr>
<tr class="odd">
<td><p>TotalServicesAmount</p></td>
<td><p>TotalServicesAmount</p></td>
</tr>
<tr class="even">
<td><p>TotalDiscountAmount</p></td>
<td><p>TotalDiscountAmount</p></td>
</tr>
<tr class="odd">
<td><p>SumMarkupFreight</p></td>
<td><p>TotalMarkupFreightAmount</p></td>
</tr>
<tr class="even">
<td><p>SumMarkupInsurance</p></td>
<td><p>TotalMarkupInsuranceAmount</p></td>
</tr>
<tr class="odd">
<td><p>SumMarkupOthers</p></td>
<td><p>TotalMarkupOtherAmount</p></td>
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
<td><p>IENum</p></td>
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
<th><p>From Table: LogisticsPostalAddress</p></th>
<th><p>To Table: FiscalDocument_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>FiscalEstablishmentPostalAddress</p></td>
</tr>
<tr class="even">
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
<th><p>From Table: VendTable</p></th>
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
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: VendInvoiceJour</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>InvoiceAddress</p></td>
<td><p>Address</p></td>
</tr>
<tr class="even">
<td><p>InvoiceCountryRegion</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>InvoiceState</p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p>InvoiceZipCode</p></td>
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
<td><p>InvoiceAddressNumber</p></td>
<td><p>StreetNumber</p></td>
</tr>
<tr class="even">
<td><p>InvoiceDistrict</p></td>
<td><p>DistrictName</p></td>
</tr>
<tr class="odd">
<td><p>InvoiceAddressComplement</p></td>
<td><p>BuildingCompliment</p></td>
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
<th><p>From Table: CustPackingSlipJour</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DeliveryAddress</p></td>
<td><p>Address</p></td>
</tr>
<tr class="even">
<td><p>DlvCountryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>DlvState</p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p>DlvZipCode</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="odd">
<td><p>DeliveryCity</p></td>
<td><p>City</p></td>
</tr>
<tr class="even">
<td><p>DeliveryStreet</p></td>
<td><p>Street</p></td>
</tr>
<tr class="odd">
<td><p>DlvAddressNumber</p></td>
<td><p>StreetNumber</p></td>
</tr>
<tr class="even">
<td><p>DlvDistrictName</p></td>
<td><p>DistrictName</p></td>
</tr>
<tr class="odd">
<td><p>DlvAddressComplement</p></td>
<td><p>BuildingCompliment</p></td>
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
<th><p>From Table: FiscalDocJour</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DeliveryAddress</p></td>
<td><p>Address</p></td>
</tr>
<tr class="even">
<td><p>DeliveryAddressCountryRegion</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>DeliveryAddressState</p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p>DeliveryAddressZipCode</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="odd">
<td><p>DeliveryAddressCity</p></td>
<td><p>City</p></td>
</tr>
<tr class="even">
<td><p>DeliveryAddressStreet</p></td>
<td><p>Street</p></td>
</tr>
<tr class="odd">
<td><p>DeliveryAddressStreetNumber</p></td>
<td><p>StreetNumber</p></td>
</tr>
<tr class="even">
<td><p>DeliveryAddressDistrict</p></td>
<td><p>DistrictName</p></td>
</tr>
<tr class="odd">
<td><p>DeliveryAddressComplement</p></td>
<td><p>BuldingCompliment</p></td>
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
<th><p>From Table: FiscalDocTrans</p></th>
<th><p>To Table: FiscalDocumentLine_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RefTableId</p></td>
<td><p>RefTableId</p></td>
</tr>
<tr class="even">
<td><p>RefRecId</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>CFOPId</p></td>
<td><p>CFOP</p></td>
</tr>
<tr class="even">
<td><p>ItemName</p></td>
<td><p>Description</p></td>
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
<td><p>InventTransId</p></td>
<td><p>InventTransId</p></td>
</tr>
<tr class="even">
<td><p>LineUnit</p></td>
<td><p>Unit</p></td>
</tr>
<tr class="odd">
<td><p>Qty</p></td>
<td><p>Quantity</p></td>
</tr>
<tr class="even">
<td><p>LineDiscAmount</p></td>
<td><p>LineDiscount</p></td>
</tr>
<tr class="odd">
<td><p>LineUnitPrice</p></td>
<td><p>UnitPrice</p></td>
</tr>
<tr class="even">
<td><p>TaxationOrigin</p></td>
<td><p>Origin</p></td>
</tr>
<tr class="odd">
<td><p>ServiceCodeId</p></td>
<td><p>ServiceCode</p></td>
</tr>
<tr class="even">
<td><p>LineUnitPrice</p></td>
<td><p>UnitPrice</p></td>
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
<th><p>From Table: FiscalDocJour</p></th>
<th><p>To Table: DEL_FiscalDocJourUpgrade_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>FiscalDocJourRecId</p></td>
</tr>
<tr class="even">
<td><p>RecVersion</p></td>
<td><p>RecVersionId</p></td>
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
<th><p>To Table: DEL_FiscalDocJourUpgrade_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>FiscalDocumentRecId</p></td>
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
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: FiscalDocJour</p></th>
<th><p>To Table: FiscalDocumentCustVendTrans_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PrimaryMethod</p></td>
<td><p>DocumentType</p></td>
</tr>
<tr class="even">
<td><p>PaymentDueDate</p></td>
<td><p>DueDate</p></td>
</tr>
<tr class="odd">
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
<th><p>From Table: FiscalDocJour</p></th>
<th><p>To Table: FiscalDocumentReferencedProcess_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ProcessAgency</p></td>
<td><p>Agency</p></td>
</tr>
<tr class="even">
<td><p>ProcessNumber</p></td>
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
<th><p>From Table: FiscalDocJour</p></th>
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
<td><p>VolumeType</p></td>
<td><p>VolumeType</p></td>
</tr>
<tr class="even">
<td><p>VolumeQty</p></td>
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

