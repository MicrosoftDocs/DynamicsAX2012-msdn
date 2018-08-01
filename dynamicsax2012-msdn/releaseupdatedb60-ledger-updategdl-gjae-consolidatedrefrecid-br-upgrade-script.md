---
title: ReleaseUpdateDB60_Ledger.updateGDL_GJAE_ConsolidatedRefRecId_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_GJAE_ConsolidatedRefRecId_BR Upgrade Script
ms:assetid: 58902d77-212f-33e9-96a6-c29250f5758d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736259(v=AX.60)
ms:contentKeyID: 49708434
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_GJAE\_ConsolidatedRefRecId\_BR Upgrade Script 


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
<td><p>updateGDL_GJAE_ConsolidatedRefRecId_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the field by fetching the corresponding record.</p></td>
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
<td><p>GeneralJournalAccountEntry</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the ConsolidatedRefRecId\_BR field in the GeneralJournalAccountEntry table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: GeneralJournalAccountEntry</p></th>
<th><p>To Table: GeneralJournalAccountEntry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>ConsolidatedRefRecid</p></td>
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
<td><p>GeneralJournalAccountEntry</p></td>
<td><p>ConsolidatedRefRecId</p></td>
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
<td><p>GeneralJournalAccountEntry</p></td>
<td><p>DEL_LedgerTransRefRecId</p></td>
</tr>
</tbody>
</table>

  


