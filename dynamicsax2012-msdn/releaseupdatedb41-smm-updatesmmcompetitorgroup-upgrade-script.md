---
title: ReleaseUpdateDB41_smm.updateSmmCompetitorGroup Upgrade Script
TOCTitle: ReleaseUpdateDB41_smm.updateSmmCompetitorGroup Upgrade Script
ms:assetid: a0a72201-f6cc-79de-588c-93567864d52a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736709(v=AX.60)
ms:contentKeyID: 49710141
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_smm.updateSmmCompetitorGroup Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_smm</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateSmmCompetitorGroup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates smmQuotationCompetitors records to point to a corresponding opportunity and updates the PartyId column based on the DEL_CompetitorId value.</p></td>
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
<td><p>smm</p></td>
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
<td><p>SalesQuotationTable</p></td>
</tr>
<tr class="even">
<td><p>smmOpportunityTable</p></td>
</tr>
<tr class="odd">
<td><p>smmQuotationCompetitorGroup</p></td>
</tr>
<tr class="even">
<td><p>smmQuotationCompetitors</p></td>
</tr>
</tbody>
</table>

  


