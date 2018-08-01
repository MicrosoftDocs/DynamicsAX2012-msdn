---
title: ReleaseUpdateDB60_Vend.createVendInvoiceInfoTable_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.createVendInvoiceInfoTable_RU Upgrade Script
ms:assetid: d63c34fe-b7c0-afc0-9cbc-a647875cc165
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687039(v=AX.60)
ms:contentKeyID: 49711487
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.createVendInvoiceInfoTable\_RU Upgrade Script [AX 2012]


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
<td><p>createVendInvoiceInfoTable_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates Russia country specific fields from &lt;c&gt;VendInvoiceInfoTable&lt;/c&gt; table to &lt;c&gt;VendInvoiceInfoTable_RU&lt;/c&gt; table</p></td>
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
<td><p>VendInvoiceInfoTable_RU</p></td>
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
<th><p>To Table: VendInvoiceInfoTable_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AgreementHeaderExt_RU</p></td>
<td><p>AgreementHeaderExt_RU</p></td>
</tr>
<tr class="even">
<td><p>AttorneyDate_RU</p></td>
<td><p>AttorneyDate_RU</p></td>
</tr>
<tr class="odd">
<td><p>AttorneyId_RU</p></td>
<td><p>AttorneyId_RU</p></td>
</tr>
<tr class="even">
<td><p>AttorneyIssuedName_RU</p></td>
<td><p>AttorneyIssuedName_RU</p></td>
</tr>
<tr class="odd">
<td><p>ConsigneeAccount_RU</p></td>
<td><p>ConsigneeAccount_RU</p></td>
</tr>
<tr class="even">
<td><p>ConsignorAccount_RU</p></td>
<td><p>ConsignorAccount_RU</p></td>
</tr>
<tr class="odd">
<td><p>Correct_RU</p></td>
<td><p>Correct_RU</p></td>
</tr>
<tr class="even">
<td><p>CorrectedFactureDate_RU</p></td>
<td><p>CorrectedFactureDate_RU</p></td>
</tr>
<tr class="odd">
<td><p>CorrectedFactureExternalId_RU</p></td>
<td><p>CorrectedFactureExternalId_RU</p></td>
</tr>
<tr class="even">
<td><p>CorrectedInvoiceDate_RU</p></td>
<td><p>CorrectedInvoiceDate_RU</p></td>
</tr>
<tr class="odd">
<td><p>CorrectedInvoiceId_RU</p></td>
<td><p>CorrectedInvoiceId_RU</p></td>
</tr>
<tr class="even">
<td><p>CorrectedPeriod_RU</p></td>
<td><p>CorrectedPeriod_RU</p></td>
</tr>
<tr class="odd">
<td><p>FactureExternalId_RU</p></td>
<td><p>FactureExternalId_RU</p></td>
</tr>
<tr class="even">
<td><p>InventProfileId_RU</p></td>
<td><p>InventProfileId_RU</p></td>
</tr>
<tr class="odd">
<td><p>InventProfileType_RU</p></td>
<td><p>InventProfileType_RU</p></td>
</tr>
<tr class="even">
<td><p>ProcessVAT</p></td>
<td><p>ProcessVAT</p></td>
</tr>
<tr class="odd">
<td><p>PurchBookVATProcessParametersRecId</p></td>
<td><p>PurchBookVATProcessParametersRecId</p></td>
</tr>
<tr class="even">
<td><p>StornoPhysical_RU</p></td>
<td><p>StornoPhysical_RU</p></td>
</tr>
<tr class="odd">
<td><p>VATChargeSource_RU</p></td>
<td><p>VATChargeSource_RU</p></td>
</tr>
<tr class="even">
<td><p>VATOnPayment_RU</p></td>
<td><p>VATOnPayment_RU</p></td>
</tr>
<tr class="odd">
<td><p>VATOperationCode_RU</p></td>
<td><p>VATOperationCode_RU</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

