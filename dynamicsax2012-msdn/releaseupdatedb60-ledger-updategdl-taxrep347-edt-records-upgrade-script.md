---
title: ReleaseUpdateDB60_Ledger.updateGDL_TaxRep347_EDT_Records Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_TaxRep347_EDT_Records Upgrade Script
ms:assetid: af199586-4e66-0e6b-7e98-5581fc71133b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686569(v=AX.60)
ms:contentKeyID: 49710523
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_TaxRep347\_EDT\_Records Upgrade Script [AX 2012]


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
<td><p>updateGDL_TaxRep347_EDT_Records</p></td>
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
<td><p>TaxRep347AddressAbbrev</p></td>
</tr>
<tr class="even">
<td><p>TaxReport347Table</p></td>
</tr>
<tr class="odd">
<td><p>TaxReport347Tenants</p></td>
</tr>
<tr class="even">
<td><p>TaxReport347Trans</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the TaxReport347Table field in the TaxReport347Tenants and TaxReport347Trans tables with the value from the RecId field of the TaxReport347Table table. Updates the TaxRep347AddressAbbrev field in the TaxReport347Tenants table with the value from the RecId field of the TaxRep347AddressAbbrev table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

