---
title: ReleaseUpdateDB60_Ledger.updateGDL_IT_EDT_Records Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_IT_EDT_Records Upgrade Script
ms:assetid: 83bfe781-4d30-8f60-66c3-f6700e314591
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685989(v=AX.60)
ms:contentKeyID: 49709441
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_IT\_EDT\_Records Upgrade Script 


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
<td><p>updateGDL_IT_EDT_Records</p></td>
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
<td><p>TaxBook</p></td>
</tr>
<tr class="even">
<td><p>TaxBookSection</p></td>
</tr>
<tr class="odd">
<td><p>TaxBookStatus</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the TaxBook field in the TaxTrans, TaxBookStatus, and TaxBookSection tables with the value from the RecId field of the TaxBook table. Updates the TaxBookSection field in the TaxTrans table with the value from the RecId field of the TaxBookSection table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

