---
title: ReleaseUpdateDB60_Ledger.updateGDL_NL_EDT_Records Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_NL_EDT_Records Upgrade Script
ms:assetid: 24ebc7f8-5275-5520-858e-caef49aed4b1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685011(v=AX.60)
ms:contentKeyID: 49707211
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_NL\_EDT\_Records Upgrade Script 


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
<td><p>updateGDL_NL_EDT_Records</p></td>
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
<td><p>LedgerJournalTrans</p></td>
</tr>
<tr class="even">
<td><p>PaymInstruction</p></td>
</tr>
<tr class="odd">
<td><p>TaxEvatError_NL</p></td>
</tr>
<tr class="even">
<td><p>TaxIntraCommCorrection_NL</p></td>
</tr>
<tr class="odd">
<td><p>TaxIntraCommDelivery_NL</p></td>
</tr>
<tr class="even">
<td><p>TaxIntraCommTable_NL</p></td>
</tr>
<tr class="odd">
<td><p>TaxReturnedError_NL</p></td>
</tr>
<tr class="even">
<td><p>TaxTurnOverLine_NL</p></td>
</tr>
<tr class="odd">
<td><p>TaxTurnOverTable_NL</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the TaxIntraCommTable\_NL field in the TaxIntraCommCorrection\_NL and TaxIntraCommDelivery\_NL tables with the value from the RecId field of the TaxIntraCommTable\_NL table. Updates the TaxTurnOverTable\_NL field in the TaxTurnOverLine\_NL table with the value from the RecId field of the TaxTurnOverTable\_NL table. Updates the TaxEvatError\_NL field in the TaxReturnedError\_NL table with the value from the RecId field of the TaxEvatError\_NL table. Updates the PaymInstruction1 field in the LedgerJournalTrans table with the value from the RecId field of the PaymInstruction table. Updates the PaymInstruction2 field in the LedgerJournalTrans table with the value from the RecId field of the PaymInstruction table. Updates the PaymInstruction3 field in the LedgerJournalTrans table with the value from the RecId field.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

