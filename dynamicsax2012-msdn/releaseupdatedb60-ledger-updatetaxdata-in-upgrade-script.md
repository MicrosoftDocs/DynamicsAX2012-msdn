---
title: ReleaseUpdateDB60_Ledger.updateTaxData_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateTaxData_IN Upgrade Script
ms:assetid: 42c62375-3214-35e4-0af7-875974dd9f1b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718855(v=AX.60)
ms:contentKeyID: 49707899
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateTaxData\_IN Upgrade Script [AX 2012]


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
<td><p>updateTaxData_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TaxData table. The record IDs of the CustomsTariffCodeTable_IN and ExciseTariffCodes_IN tables are now stored in place of the CustomsTariffCode_IN and TariffCode_IN values.</p></td>
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
<td><p>SalesTaxFormTypes_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxData</p></td>
</tr>
<tr class="odd">
<td><p>CustomsTariffCodeTable_IN</p></td>
</tr>
<tr class="even">
<td><p>ExciseTariffCodes_IN</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

