---
title: ReleaseUpdateDB60_Ledger.updateExciseRG23CRegister_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateExciseRG23CRegister_IN Upgrade Script
ms:assetid: 0928e7ce-0bf8-3a0f-8ac3-f584bbae1fdb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684804(v=AX.60)
ms:contentKeyID: 49706498
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateExciseRG23CRegister\_IN Upgrade Script 


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
<td><p>updateExciseRG23CRegister_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ExciseRG23CRegister_IN table. The values of the RecId field of the TaxRegistrationNumberTable_IN and TaxComponentTable_IN tables are now stored in place of the ECCNumber and TaxComponent values.</p></td>
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
<td><p>ExciseRG23CRegister_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxComponentTable_IN</p></td>
</tr>
<tr class="odd">
<td><p>TaxRegistrationNumberTable_IN</p></td>
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
<th><p>From Table: TaxRegistrationNumberTable_IN</p></th>
<th><p>To Table: ExciseRG23CRegister_IN</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Recid</p></td>
<td><p>TaxRegistrationNumberTable</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TaxComponentTable_IN</p></th>
<th><p>To Table: ExciseRG23CRegister_IN</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>TaxComponentTable</p></td>
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
<td><p>ExciseRG23CRegister_IN</p></td>
<td><p>TaxRegistrationNumberTable</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>ExciseRG23CRegister_IN</p></td>
<td><p>TaxComponentTable</p></td>
<td><p>RefRecId</p></td>
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
<td><p>ExciseRG23CRegister_IN</p></td>
<td><p>del_eccNumber</p></td>
</tr>
<tr class="even">
<td><p>ExciseRG23CRegister_IN</p></td>
<td><p>del_TaxComponent</p></td>
</tr>
</tbody>
</table>

  


