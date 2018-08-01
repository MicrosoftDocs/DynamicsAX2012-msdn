---
title: ReleaseUpdateDB60_Ledger.createTaxTrans_W Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.createTaxTrans_W Upgrade Script
ms:assetid: 8df35395-0f50-cfb1-f4c8-4fbddcf9223d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736495(v=AX.60)
ms:contentKeyID: 49709685
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.createTaxTrans\_W Upgrade Script [AX 2012]


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
<td><p>createTaxTrans_W</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates country specific fields from the TaxTrans table to the TaxTrans_W table.</p></td>
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
<td><p>TaxTrans</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans_W</p></td>
</tr>
<tr class="odd">
<td><p>TaxComponentTable_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxRegistrationNumbers_IN</p></td>
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
<td><p>TaxTrans_W</p></td>
<td><p>AbatementAmount_IN</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TaxTrans_W</p></td>
<td><p>Addressing_PL</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans_W</p></td>
<td><p>ApplyExcise_IN</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TaxTrans_W</p></td>
<td><p>ClaimPercentage_IN</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans_W</p></td>
<td><p>CustomsDuty_IN</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TaxTrans_W</p></td>
<td><p>CustVendName_PL</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans_W</p></td>
<td><p>DocumentDate_PL</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TaxTrans_W</p></td>
<td><p>ExciseAmount_PL</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans_W</p></td>
<td><p>PostponeVAT_CZ</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TaxTrans_W</p></td>
<td><p>TaxAmountCustoms_IN</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans_W</p></td>
<td><p>TaxComponentTable_IN</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TaxTrans_W</p></td>
<td><p>TaxPeriodPaymentCode_PL</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans_W</p></td>
<td><p>TaxRegistrationNumberTable_IN</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TaxTrans_W</p></td>
<td><p>TaxType_IN</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans_W</p></td>
<td><p>VatDueDate_W</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TaxTrans_W</p></td>
<td><p>VATNum_PL</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TaxTrans</p></td>
<td><p>AbatementAmount_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
<td><p>Addressing_PL</p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans</p></td>
<td><p>ApplyExcise_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
<td><p>ClaimPercentage_IN</p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans</p></td>
<td><p>CustomsDuty_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
<td><p>CustVendName_PL</p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans</p></td>
<td><p>DocumentDate_PL</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
<td><p>ExciseAmount_PL</p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans</p></td>
<td><p>PostponeVAT_CZ</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
<td><p>TaxAmountCustoms_IN</p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans</p></td>
<td><p>TaxComponentTable_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
<td><p>TaxPeriodPaymentCode_PL</p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans</p></td>
<td><p>TaxRegistrationNumberTable_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
<td><p>TaxType_IN</p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans</p></td>
<td><p>VatDueDate_W</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
<td><p>vatNum_PL</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

