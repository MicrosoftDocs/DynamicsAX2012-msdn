---
title: ReleaseUpdateDB60_Ledger.updateLedgerStatement_CZ Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerStatement_CZ Upgrade Script
ms:assetid: aa08c7b1-100f-3bc0-26c9-1e121b1f9246
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686446(v=AX.60)
ms:contentKeyID: 49710402
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerStatement\_CZ Upgrade Script 


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
<td><p>updateLedgerStatement_CZ</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Performs the conversion from the old tables to the new tables and from the old fields to the new fields.</p></td>
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
<td><p>Fixed Asset</p></td>
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
<td><p>LedgerStatementHeader</p></td>
</tr>
<tr class="even">
<td><p>LedgerStatementDefinition</p></td>
</tr>
</tbody>
</table>


## Remarks

The balance field that was serving as both a line reference and an indicator to reverse the sign has been split into separate fields.

## Name Changes for Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Old Table Name: CzLedgerStatementHeader</p></th>
<th><p>New Table Name: LedgerStatementHeader</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>Txt</p></td>
<td><p>Text</p></td>
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
<th><p>Old Table Name: CzLedgerStatementDefinition</p></th>
<th><p>New Table Name: LedgerStatementDefinition</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>Line</p></td>
<td><p>LedgerStatementHeader</p></td>
</tr>
<tr class="odd">
<td><p>AccountNum</p></td>
<td><p>MainAccount</p></td>
</tr>
<tr class="even">
<td><p>Balance</p></td>
<td><p>LineReference</p></td>
</tr>
<tr class="odd">
<td><p>Balance</p></td>
<td><p>ReverseSign</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

