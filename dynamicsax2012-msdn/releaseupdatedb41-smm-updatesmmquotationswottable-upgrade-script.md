---
title: ReleaseUpdateDB41_smm.updateSmmQuotationSwotTable Upgrade Script
TOCTitle: ReleaseUpdateDB41_smm.updateSmmQuotationSwotTable Upgrade Script
ms:assetid: 52c1a429-5590-1366-c145-01864db37ee9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736101(v=AX.60)
ms:contentKeyID: 49708278
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_smm.updateSmmQuotationSwotTable Upgrade Script 


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
<td><p>updateSmmQuotationSwotTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates one or more entries in the smmSWOTTable, for each record in the smmQuotationSWOTTable that is associated with a Quotation, Project, or Campaign entry, that represent the Strength, Weakness, Opportunity, and Threat notes in separate records.</p></td>
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
<td><p>DEL_smmQuotationSwotTable</p></td>
</tr>
<tr class="even">
<td><p>ProjTable</p></td>
</tr>
<tr class="odd">
<td><p>SalesQuotationTable</p></td>
</tr>
<tr class="even">
<td><p>smmCampaignTable</p></td>
</tr>
<tr class="odd">
<td><p>smmOpportunityTable</p></td>
</tr>
<tr class="even">
<td><p>smmSwotTable</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

