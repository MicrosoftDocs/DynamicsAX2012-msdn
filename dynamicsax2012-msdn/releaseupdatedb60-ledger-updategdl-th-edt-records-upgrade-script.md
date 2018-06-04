---
title: ReleaseUpdateDB60_Ledger.updateGDL_TH_EDT_Records Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_TH_EDT_Records Upgrade Script
ms:assetid: 83453ec3-e30b-8394-a7a3-9ab9f2023143
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685974(v=AX.60)
ms:contentKeyID: 49709427
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_TH\_EDT\_Records Upgrade Script 


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
<td><p>updateGDL_TH_EDT_Records</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Thai Withholding EDT relations with the RecId table-based relations.</p></td>
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
<td><p>LedgerJournalTrans</p></td>
</tr>
<tr class="even">
<td><p>TaxWithholdItemGroupHeading_TH</p></td>
</tr>
<tr class="odd">
<td><p>TaxWithholdLedgerAccountGroup_TH</p></td>
</tr>
<tr class="even">
<td><p>TaxWithholdOnItem_TH</p></td>
</tr>
<tr class="odd">
<td><p>TaxWithholdPeriodHead_TH</p></td>
</tr>
<tr class="even">
<td><p>TaxWithholdReportPeriod_TH</p></td>
</tr>
<tr class="odd">
<td><p>TaxWithholdReportSetup_TH</p></td>
</tr>
<tr class="even">
<td><p>TaxWithholdReportVoucher_TH</p></td>
</tr>
<tr class="odd">
<td><p>TaxWithholdRevenueTable_TH</p></td>
</tr>
<tr class="even">
<td><p>TaxWithholdTable</p></td>
</tr>
<tr class="odd">
<td><p>TaxWithholdTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the TaxWithholdItemGroupHeading\_TH field in the LedgerJournalTrans, TaxWithholdReportSetup\_TH, taxWithholdOnItem\_TH, and TaxWithholdTrans tables with the value from the RecId field of the TaxWithholdItemGroupHeading\_TH table. Updates the TaxWithholdPeriodHead\_TH field in the TaxWithholdReportPeriod\_TH, TaxWithholdTrans, and taxWithholdTrans tables with the value from the RecId field of the TaxWithholdPeriodHead\_TH table. Updates the TaxWithholdLedgerAccountGroup\_TH field in the TaxWithholdTable table with the value from the RecId field of the TaxWithholdLedgerAccountGroup\_TH table. Updates the TaxWithholdRevenueTable\_TH field in the TaxWithholdItemGroupHeading\_TH table with the value from the RecId field of the taxWithholdRevenueTable\_TH table. Updates the CustAccount field in the TaxWithholdTrans table with the value from the del\_CustAccount\_TH field of the TaxWithholdTrans table. Before Microsoft Dynamics AX 2012 there could be the case that a record could be created for Thai and non-Thai customer. However, in the current version, the Thai withholding tax is limited to Thai legal entity,and there is no need for a Thai specific column.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

