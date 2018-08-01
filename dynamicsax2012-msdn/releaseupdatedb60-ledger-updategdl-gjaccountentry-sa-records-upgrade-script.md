---
title: ReleaseUpdateDB60_Ledger.updateGDL_GJAccountEntry_SA_Records Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_GJAccountEntry_SA_Records Upgrade Script
ms:assetid: 3efa38ae-2811-39cd-8629-65405184998d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718778(v=AX.60)
ms:contentKeyID: 49707814
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_GJAccountEntry\_SA\_Records Upgrade Script 


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
<td><p>updateGDL_GJAccountEntry_SA_Records</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the field by retrieving the corresponding record from the LedgerTrans table.</p></td>
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
<td><p>DEL_LedgerTrans</p></td>
</tr>
<tr class="even">
<td><p>GeneralJournalAccountEntry</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the ProjId\_SA field in the GeneralJournalAccountEntry table with the value from the DEL\_ProjId\_SA field in the LedgerTrans table.

  


