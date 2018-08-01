---
title: ReleaseUpdateDB60_Ledger.updateLedgerTableStatus_ES Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerTableStatus_ES Upgrade Script
ms:assetid: 0bc0f449-9804-318e-301b-177736f51bd8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735656(v=AX.60)
ms:contentKeyID: 49706567
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerTableStatus\_ES Upgrade Script [AX 2012]


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
<td><p>updateLedgerTableStatus_ES</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates ActiveFrom and ActiveTo fields in the DimensionAttributeValue table.</p></td>
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
<td><p>DimensionAttributeValue</p></td>
</tr>
</tbody>
</table>


## Remarks

The Status field of the LedgerTable table is renamed to the DEL\_Status\_ES field and the DimensionAttributeValue table records are modified for accounts with the corresponding status of old, change, or new. If the value of the Status field of the LedgerTable is old or change, then the value of the ActiveTo field will be set to December 31, 2007. If the value of the Status field of the LedgerTable is new, then the value of the ActiveFrom field will be set to January 1, 2008. If the value of the Status field of the LedgerTable is blank, then no action is taken.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

