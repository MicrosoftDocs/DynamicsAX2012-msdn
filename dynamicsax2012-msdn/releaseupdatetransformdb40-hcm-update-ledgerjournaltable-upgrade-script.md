---
title: ReleaseUpdateTransformDB40_HCM.update_LedgerJournalTable Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_HCM.update_LedgerJournalTable Upgrade Script
ms:assetid: 9f62d324-e8aa-7082-e078-965c0f887f5e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736676(v=AX.60)
ms:contentKeyID: 49710108
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_HCM.update\_LedgerJournalTable Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_HCM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>update_LedgerJournalTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates approver data for the shadow table of the LedgerJournalTable table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>LedgerJournalTable</p></td>
</tr>
<tr class="even">
<td><p>HcmWorker</p></td>
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
<th><p>From Table: HcmWorker</p></th>
<th><p>To Table: Shadow_LedgerJournalTable_HCM</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>Approver</p></td>
</tr>
</tbody>
</table>

  


