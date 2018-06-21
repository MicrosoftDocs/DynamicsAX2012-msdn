---
title: ReleaseUpdateDB60_Invent.updateGDL_IT_EDT_Records Upgrade Script
TOCTitle: ReleaseUpdateDB60_Invent.updateGDL_IT_EDT_Records Upgrade Script
ms:assetid: a8d6af58-f8ad-a532-459e-a807f197c0a9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686403(v=AX.60)
ms:contentKeyID: 49710359
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.updateGDL\_IT\_EDT\_Records Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Invent</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateGDL_IT_EDT_Records</p></td>
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
<td><p>Inventory management</p></td>
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
<td><p>InventFiscalLIFOGroup</p></td>
</tr>
<tr class="even">
<td><p>InventFiscalLIFOJournalTrans</p></td>
</tr>
<tr class="odd">
<td><p>InventFiscalLIFOJournalTransAdj</p></td>
</tr>
<tr class="even">
<td><p>InventTable</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the InventFiscalLIFOGroup field in the InventFiscalLIFOJournalTrans, InventFiscalLIFOJournalTransAdj, and InventTable tables with the value from the RecId field of the InventFiscalLIFOGroup table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

