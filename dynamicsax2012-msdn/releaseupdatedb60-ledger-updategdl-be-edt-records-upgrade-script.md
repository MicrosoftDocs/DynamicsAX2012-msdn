---
title: ReleaseUpdateDB60_Ledger.updateGDL_BE_EDT_Records Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_BE_EDT_Records Upgrade Script
ms:assetid: 49b19c8f-421c-5ee4-dc94-6e7805e1daf6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685354(v=AX.60)
ms:contentKeyID: 49708059
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_BE\_EDT\_Records Upgrade Script 


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
<td><p>updateGDL_BE_EDT_Records</p></td>
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
<td><p>Ledger</p></td>
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
<td><p>TaxEdivatDetail</p></td>
</tr>
<tr class="even">
<td><p>TaxEdivatErrors</p></td>
</tr>
<tr class="odd">
<td><p>TaxEdivatGeneral</p></td>
</tr>
<tr class="even">
<td><p>TaxEdivatReturnedErrors</p></td>
</tr>
<tr class="odd">
<td><p>TaxIntervatDetail</p></td>
</tr>
<tr class="even">
<td><p>TaxIntervatGeneral</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the TaxIntervatGeneral field in the TaxIntervatDetail table with the value from the RecId field of the TaxIntervatGeneral table. Updates the TaxEdivatErrors field in the TaxEdivatReturnedErrors table with the value from the RecId field of the TaxEdivatErrors table. Updates the TaxEdivatGeneral field in the TaxEdivatReturnedErrors and TaxEdivatDetail tables with the value from the RecId field of the TaxEdivatGeneral table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

