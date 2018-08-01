---
title: ReleaseUpdateDB60_Basic.updateNumberSequenceTableReference Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateNumberSequenceTableReference Upgrade Script
ms:assetid: 01aaa579-56c1-bce1-9d6e-8275f3ea92d8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684630(v=AX.60)
ms:contentKeyID: 49706327
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateNumberSequenceTableReference Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateNumberSequenceTableReference</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates references to the NumberSequenceTable table as a result of the primary key being changed for that table. Constructs a number sequence for each extended data type.</p></td>
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
<td><p>Basic</p></td>
</tr>
<tr class="even">
<td><p>Project</p></td>
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
<td><p>ProjJournalName</p></td>
</tr>
<tr class="even">
<td><p>ProjJournalTable</p></td>
</tr>
<tr class="odd">
<td><p>ProjInvoiceJour</p></td>
</tr>
<tr class="even">
<td><p>NumberSequenceTable</p></td>
</tr>
<tr class="odd">
<td><p>NumberSequenceScope</p></td>
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
<th><p>From Table: NumberSequenceTable</p></th>
<th><p>To Table: ProjJournalName</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>VoucherNumberSequenceTable</p></td>
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
<th><p>From Table: NumberSequenceTable</p></th>
<th><p>To Table: ProjJournalTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>VoucherNumberSequenceTable</p></td>
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
<th><p>From Table: NumberSequenceTable</p></th>
<th><p>To Table: ProjInvoiceJour</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>VoucherNumberSequenceTable</p></td>
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
<td><p>ProjJournalName</p></td>
<td><p>VoucherNumberSequenceTable</p></td>
<td><p>ProjVoucherNumberSequenceTable</p></td>
</tr>
<tr class="even">
<td><p>ProjJournalTable</p></td>
<td><p>VoucherNumberSequenceTable</p></td>
<td><p>ProjVoucherNumberSequenceTable</p></td>
</tr>
<tr class="odd">
<td><p>ProjInvoiceJour</p></td>
<td><p>VoucherNumberSequenceTable</p></td>
<td><p>ProjVoucherNumberSequenceTable</p></td>
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
<td><p>ProjJournalName</p></td>
<td><p>DEL_VoucherSeqId</p></td>
</tr>
<tr class="even">
<td><p>ProjJournalTable</p></td>
<td><p>DEL_VoucherSeqId</p></td>
</tr>
<tr class="odd">
<td><p>ProjInvoiceJour</p></td>
<td><p>DEL_VoucherSequenceCode</p></td>
</tr>
</tbody>
</table>

  


