---
title: ReleaseUpdateDB60_Ledger.updateIntrastatArchiveGeneral Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateIntrastatArchiveGeneral Upgrade Script
ms:assetid: ab7ce643-7e89-5ae2-5f7b-ab4cab2675b5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686478(v=AX.60)
ms:contentKeyID: 49710433
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateIntrastatArchiveGeneral Upgrade Script 


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
<td><p>updateIntrastatArchiveGeneral</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the time and date information for the IntrastatArchiveGeneral table.</p></td>
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
<td><p>IntrastatArchiveGeneral</p></td>
</tr>
</tbody>
</table>


## Remarks

The taxPreparationDate and taxPreparationTime fields in the IntrastatArchiveGeneral table have been deleted and the createdDateTime fields now stores these values.

  


