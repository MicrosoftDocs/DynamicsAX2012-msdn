---
title: ReleaseUpdateDB60_Ledger.updateGDL_NO_EDTRecords Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_NO_EDTRecords Upgrade Script
ms:assetid: cd9c0d8a-4348-6e03-687b-f4dc1accf555
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719733(v=AX.60)
ms:contentKeyID: 49711299
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_NO\_EDTRecords Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>updateGDL_NO_EDTRecords</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the surrogate key column in the foreign tables with the value from the RecId field of the primary table.</p></td>
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
<td><p>BankCustPaymIdTable</p></td>
</tr>
<tr class="even">
<td><p>BankFileArchFileTypeTable</p></td>
</tr>
<tr class="odd">
<td><p>BankFileArchParameters</p></td>
</tr>
<tr class="even">
<td><p>BankFileArchTable</p></td>
</tr>
<tr class="odd">
<td><p>CustEinvoiceHeader</p></td>
</tr>
<tr class="even">
<td><p>CustEinvoiceIntegration</p></td>
</tr>
<tr class="odd">
<td><p>CustEinvoiceIntegrationError</p></td>
</tr>
<tr class="even">
<td><p>CustEinvoiceIntegrationPaymModeChg</p></td>
</tr>
<tr class="odd">
<td><p>CustEinvoiceIntegrationTrans</p></td>
</tr>
<tr class="even">
<td><p>CustEinvoiceIntegrationTypeTable</p></td>
</tr>
<tr class="odd">
<td><p>CustEinvoiceLines</p></td>
</tr>
<tr class="even">
<td><p>CustEinvoiceTable</p></td>
</tr>
<tr class="odd">
<td><p>CustGroup</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the BankFileArchFileTypeTable field in the BankFileArchParameters table with the value from the RecId field of the BankFileArchFileTypeTable table. Updates the BankFileArchFileTypeTable field in the BankFileArchTable tabke with the value from the RecId field of the BankFileArchFileTypeTable table. Updates the CustEinvoiceTable field in the CustEinvoiceHeader table with the value from the RecId field of the CustEinvoiceTable table. Updates the CustEinvoiceTable field in the CustEinvoiceLines table with the value from the RecId field of the CustEinvoiceTable table. Updates the CustEinvoiceIntegrationTypeTable field in the custEinvoiceIntegration table with the value from the RecId field of the CustEinvoiceIntegrationTypeTable table. Updates the CustEinvoiceIntegrationTypeTable field in the CustEinvoiceIntegrationPaymModeChg table with the value from the RecId field of the CustEinvoiceIntegrationTypeTable table. Updates the CustEinvoiceIntegrationTypeTable field in the CustEinvoiceIntegrationTrans table with the value from the RecId field of the CustEinvoiceIntegrationTypeTable table. Updates the CustEinvoiceIntegrationError field in the CustEinvoiceIntegrationTrans table with the value from the RecId field of the custEinvoiceIntegrationError table. Updates the BankFileArchTable field in the CustEinvoiceIntegrationTrans table with the value from the RecId field of the BankFileArchTable table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

