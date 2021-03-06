﻿---
title: ReleaseUpdateDB60_Ledger.updateMainAcctParent_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateMainAcctParent_BR Upgrade Script
ms:assetid: f619ff3a-e451-48f0-8ed0-3d89398ce83d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737586(v=AX.60)
ms:contentKeyID: 49712279
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateMainAcctParent\_BR Upgrade Script 


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
<td><p>updateMainAcctParent_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This method updates the ParentMainAccount_BR field from the MainAccount table. This field existed in the LedgerTable table in previous versions of Ax.</p></td>
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
<td><p>MainAccount</p></td>
</tr>
</tbody>
</table>


## Remarks

In Ax2012 there is a new MainAccount table. This table replaces the LedgerTable table, which used to keep the Brazilian ParentAccount\_BR field. This field was therefore moved to the MainAccount table in Ax2012 under the name ParentMainAccount\_BR. This upgrade script moves the content from the DEL\_LedgerTable.ParentAccount\_BR field to the MainAccount.ParentMainAccount\_BR field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_LedgerTable</p></th>
<th><p>To Table: MainAccount</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ParentAccount_BR</p></td>
<td><p>ParentMainAccount_BR</p></td>
</tr>
</tbody>
</table>

  


