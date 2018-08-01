---
title: ReleaseUpdateDB60_Ledger.updateTaxTrans_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateTaxTrans_IN Upgrade Script
ms:assetid: 6f1134e9-c63c-1719-bd58-9640076a3c29
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685753(v=AX.60)
ms:contentKeyID: 49708953
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateTaxTrans\_IN Upgrade Script [AX 2012]


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
<td><p>updateTaxTrans_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the foreign key fields in the TaxTrans table with the value from the RecId field of the TaxComponentTable_IN and TaxRegistrationNumberTable_IN primary tables.</p></td>
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
<td><p>TaxComponentTable_IN</p></td>
</tr>
<tr class="odd">
<td><p>TaxRegistrationNumberTable_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the TaxComponentTable\_IN TaxRegistrationNumberTable\_IN fields in the TaxTrans table with the value from the RecId field in the TaxComponentTable\_IN and TaxRegistrationNumberTable\_IN tables respectively.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

