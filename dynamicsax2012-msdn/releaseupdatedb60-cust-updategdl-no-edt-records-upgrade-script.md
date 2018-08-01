---
title: ReleaseUpdateDB60_Cust.updateGDL_NO_EDT_Records Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateGDL_NO_EDT_Records Upgrade Script
ms:assetid: 2eae19be-4d09-b953-d1ab-1a8911cf6bc2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736017(v=AX.60)
ms:contentKeyID: 49707432
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateGDL\_NO\_EDT\_Records Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>updateGDL_NO_EDT_Records</p></td>
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
<td><p>CustGroup</p></td>
</tr>
<tr class="even">
<td><p>BankCustPaymIdTable</p></td>
</tr>
<tr class="odd">
<td><p>CustParameters</p></td>
</tr>
<tr class="even">
<td><p>CustTable</p></td>
</tr>
<tr class="odd">
<td><p>CustPaymModeTable</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the BankCustPaymIdTable column in the CustGroup, BankCustPaymIdTable, CustParameters, and CustTable table with the value from the RecId field of the CustPaymModeTable table based on the value of the del\_PaymIdType column.

  


