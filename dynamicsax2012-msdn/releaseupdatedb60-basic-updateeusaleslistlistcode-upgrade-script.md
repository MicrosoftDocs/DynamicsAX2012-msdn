---
title: ReleaseUpdateDB60_Basic.updateEUSalesListListCode Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateEUSalesListListCode Upgrade Script
ms:assetid: dca8d055-4aeb-a35d-a82a-08af8e5f19b1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737196(v=AX.60)
ms:contentKeyID: 49711639
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateEUSalesListListCode Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateEUSalesListListCode</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates all tables that use the ListCode enumeration, to deprecate the use of the EUService enumeration value.</p></td>
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
<td><p>Basic</p></td>
</tr>
<tr class="even">
<td><p>Accounts payable</p></td>
</tr>
<tr class="odd">
<td><p>Accounts receivable</p></td>
</tr>
<tr class="even">
<td><p>Project</p></td>
</tr>
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
<td><p>LedgerJournalTrans</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceJour</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceTable</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceTemplate</p></td>
</tr>
<tr class="odd">
<td><p>CustPackingSlipJour</p></td>
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
<td><p>PurchTable</p></td>
</tr>
<tr class="even">
<td><p>PurchTableHistory</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoiceJour</p></td>
</tr>
<tr class="even">
<td><p>SalesQuotationTable</p></td>
</tr>
<tr class="odd">
<td><p>SalesTable</p></td>
</tr>
<tr class="even">
<td><p>CzCustAdvanceInvoiceTable</p></td>
</tr>
<tr class="odd">
<td><p>TaxIntraCommCorrection_NL</p></td>
</tr>
<tr class="even">
<td><p>TaxIntraCommDelivery_NL</p></td>
</tr>
<tr class="odd">
<td><p>RCSalesList_UK</p></td>
</tr>
<tr class="even">
<td><p>EUSalesList</p></td>
</tr>
</tbody>
</table>


## Remarks

For the listed tables, any use of the EUService enumeration value is replaced by the EUSales enumeration value. For the EUSalesList table, the AmountMST value is added to the ServiceAmountMST field, and the AmountMST field is set to 0, when the EUService enumeration value was used.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

