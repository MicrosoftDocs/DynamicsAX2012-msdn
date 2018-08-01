---
title: ReleaseUpdateDB60_Basic.updateDirPartyAddress_RU_Fields_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateDirPartyAddress_RU_Fields_RU Upgrade Script
ms:assetid: 03859e40-45d5-f244-c9f2-9eb2ce35c849
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684673(v=AX.60)
ms:contentKeyID: 49706369
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateDirPartyAddress\_RU\_Fields\_RU Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateDirPartyAddress_RU_Fields_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates release update address fields to the new global address book.</p></td>
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
<tr class="even">
<td><p>Accounts payable</p></td>
</tr>
<tr class="odd">
<td><p>Bank</p></td>
</tr>
<tr class="even">
<td><p>Basic</p></td>
</tr>
<tr class="odd">
<td><p>Project</p></td>
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
<td><p>CompanyInfo</p></td>
</tr>
<tr class="even">
<td><p>CustTable</p></td>
</tr>
<tr class="odd">
<td><p>VendTable</p></td>
</tr>
<tr class="even">
<td><p>ContactPerson</p></td>
</tr>
<tr class="odd">
<td><p>BankAccountTable</p></td>
</tr>
<tr class="even">
<td><p>BankGroup</p></td>
</tr>
<tr class="odd">
<td><p>CustBankAccount</p></td>
</tr>
<tr class="even">
<td><p>VendBankAccount</p></td>
</tr>
<tr class="odd">
<td><p>SalesTable</p></td>
</tr>
<tr class="even">
<td><p>SalesLine</p></td>
</tr>
<tr class="odd">
<td><p>PurchTable</p></td>
</tr>
<tr class="even">
<td><p>PurchLine</p></td>
</tr>
<tr class="odd">
<td><p>CustCollectionLetterJour</p></td>
</tr>
<tr class="even">
<td><p>CustConfirmJour</p></td>
</tr>
<tr class="odd">
<td><p>CustInterestJour</p></td>
</tr>
<tr class="even">
<td><p>CustInvoice4PaymJour_RU</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceJour</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceTable</p></td>
</tr>
<tr class="odd">
<td><p>CustPackingSlipJour</p></td>
</tr>
<tr class="even">
<td><p>CustQuotationConfirmJour</p></td>
</tr>
<tr class="odd">
<td><p>CustQuotationJour</p></td>
</tr>
<tr class="even">
<td><p>ECPCustSignUp</p></td>
</tr>
<tr class="odd">
<td><p>IntrastatServicePoint_FI</p></td>
</tr>
<tr class="even">
<td><p>ProjInvoiceJour</p></td>
</tr>
<tr class="odd">
<td><p>ProjInvoiceTable</p></td>
</tr>
<tr class="even">
<td><p>ProjProposalJour</p></td>
</tr>
<tr class="odd">
<td><p>ProjTable</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqTable</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQCaseLine</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQCaseTable</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQLine</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQTable</p></td>
</tr>
<tr class="even">
<td><p>SalesBasket</p></td>
</tr>
<tr class="odd">
<td><p>SalesCarrier</p></td>
</tr>
<tr class="even">
<td><p>SalesQuotationLine</p></td>
</tr>
<tr class="odd">
<td><p>SalesQuotationTable</p></td>
</tr>
<tr class="even">
<td><p>SMAServiceOrderTable</p></td>
</tr>
<tr class="odd">
<td><p>smmBusRelTable</p></td>
</tr>
<tr class="even">
<td><p>Tax1099SoftwareVendParameters</p></td>
</tr>
<tr class="odd">
<td><p>Tax1099TransmitterParameters</p></td>
</tr>
<tr class="even">
<td><p>TaxAuthorityAddress</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoice4PaymJour_RU</p></td>
</tr>
<tr class="even">
<td><p>VendPackingSlipJour</p></td>
</tr>
<tr class="odd">
<td><p>VendPurchOrderJour</p></td>
</tr>
<tr class="even">
<td><p>VendReceiptsListJour</p></td>
</tr>
<tr class="odd">
<td><p>VendRFQJour</p></td>
</tr>
<tr class="even">
<td><p>DEL_AddressTrans_RU</p></td>
</tr>
<tr class="odd">
<td><p>IntrastatParameters</p></td>
</tr>
<tr class="even">
<td><p>LogisticsAddresssCity</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsAddressDistrict</p></td>
</tr>
<tr class="even">
<td><p>LogisticsAddressStreet_RU</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsAddressHouseNumber_RU</p></td>
</tr>
<tr class="even">
<td><p>LogisticsAddressFlatNumber_RU</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsLocation</p></td>
</tr>
<tr class="even">
<td><p>LogisticsLocationPostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsPostalAddress</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

