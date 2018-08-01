---
title: ReleaseUpdateDB60_Ledger.updateCityElectronicFiscalDocument_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateCityElectronicFiscalDocument_BR Upgrade Script
ms:assetid: 540c6c2d-463b-dc7f-1022-a0f748e8b588
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736141(v=AX.60)
ms:contentKeyID: 49708317
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateCityElectronicFiscalDocument\_BR Upgrade Script 


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
<td><p>updateCityElectronicFiscalDocument_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Create entries for city electronic fiscal documents in the new fiscal document module.</p></td>
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
<td><p>EFDocumentCity_BR</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: FiscalDocJour_BR</p></th>
<th><p>To Table: EFDocumentCity_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EletronicInvoiceValidationNum</p></td>
<td><p>rpsValidationNumber</p></td>
</tr>
<tr class="even">
<td><p>EletronicInvoiceId</p></td>
<td><p>rpsNumber</p></td>
</tr>
<tr class="odd">
<td><p>ElectronicInvoiceDateTime</p></td>
<td><p>rpsDate</p></td>
</tr>
<tr class="even">
<td><p>rpsType</p></td>
<td><p>rpsType</p></td>
</tr>
<tr class="odd">
<td><p>rpsStatus</p></td>
<td><p>rpsStatus</p></td>
</tr>
<tr class="even">
<td><p>rpsSendDateTime</p></td>
<td><p>rpsExportDate</p></td>
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
<td><p>EFDocumentCity_BR</p></td>
<td><p></p></td>
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
<td><p>FiscalDocJour_BR</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


