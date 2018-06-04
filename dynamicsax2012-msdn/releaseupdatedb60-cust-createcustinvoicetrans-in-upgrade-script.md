---
title: ReleaseUpdateDB60_Cust.createCustInvoiceTrans_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.createCustInvoiceTrans_IN Upgrade Script
ms:assetid: a776491a-74e8-7592-62ac-cfe6020a31f3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686355(v=AX.60)
ms:contentKeyID: 49710311
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.createCustInvoiceTrans\_IN Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>createCustInvoiceTrans_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates India country specific fields from &lt;c&gt;CustInvoiceTrans&lt;/c&gt; table to &lt;c&gt;CustInvoiceTrans_IN&lt;/c&gt; table</p></td>
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
<td><p>CustInvoiceTrans</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceTrans_IN</p></td>
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
<th><p>From Table: CustInvoiceTrans</p></th>
<th><p>To Table: CustInvoiceTrans_IN</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AssessableValue_IN</p></td>
<td><p>AssessableValue_IN</p></td>
</tr>
<tr class="even">
<td><p>CompanyLocation_IN</p></td>
<td><p>CompanyLocation_IN</p></td>
</tr>
<tr class="odd">
<td><p>CreditNoteDate_IN</p></td>
<td><p>CreditNoteDate_IN</p></td>
</tr>
<tr class="even">
<td><p>CustomsTariffCodeTable_IN</p></td>
<td><p>CustomsTariffCodeTable_IN</p></td>
</tr>
<tr class="odd">
<td><p>DirectSettlement_IN</p></td>
<td><p>DirectSettlement_IN</p></td>
</tr>
<tr class="even">
<td><p>DSA_IN</p></td>
<td><p>DSA_IN</p></td>
</tr>
<tr class="odd">
<td><p>ExciseRecordType_IN</p></td>
<td><p>ExciseRecordType_IN</p></td>
</tr>
<tr class="even">
<td><p>ExciseTariffCodes_IN</p></td>
<td><p>ExciseTariffCodes_IN</p></td>
</tr>
<tr class="odd">
<td><p>ExciseType_IN</p></td>
<td><p>ExciseType_IN</p></td>
</tr>
<tr class="even">
<td><p>RegistrationLocation_IN</p></td>
<td><p>RegistrationLocation_IN</p></td>
</tr>
<tr class="odd">
<td><p>RegistrationPostalAddress_IN</p></td>
<td><p>RegistrationPostalAddress_IN</p></td>
</tr>
<tr class="even">
<td><p>SalesTaxFormTypes_IN</p></td>
<td><p>SalesTaxFormTypes_IN</p></td>
</tr>
<tr class="odd">
<td><p>ServiceCodeTable_IN</p></td>
<td><p>ServiceCodeTable_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxInformation_IN</p></td>
<td><p>TaxInformation_IN</p></td>
</tr>
<tr class="odd">
<td><p>TaxInventVATCommodityCode_IN</p></td>
<td><p>TaxInventVATCommodityCode_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxWithholdLineNum_IN</p></td>
<td><p>TaxWithholdLineNum_IN</p></td>
</tr>
<tr class="odd">
<td><p>TaxWithholdReturn_IN</p></td>
<td><p>TaxWithholdReturn_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxWithholdVoucher_IN</p></td>
<td><p>TaxWithholdVoucher_IN</p></td>
</tr>
<tr class="odd">
<td><p>TCSGroup_IN</p></td>
<td><p>TCSGroup_IN</p></td>
</tr>
<tr class="even">
<td><p>TDSGroup_IN</p></td>
<td><p>TDSGroup_IN</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

