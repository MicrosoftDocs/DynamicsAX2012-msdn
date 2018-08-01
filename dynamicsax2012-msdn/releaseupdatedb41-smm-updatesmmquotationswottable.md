---
title: ReleaseUpdateDB41_smm.updateSmmQuotationSwotTable
TOCTitle: ReleaseUpdateDB41_smm.updateSmmQuotationSwotTable
ms:assetid: 6542d91a-15ec-ba63-b0e8-239c99b1a588
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719211(v=AX.60)
ms:contentKeyID: 49708750
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_smm.updateSmmQuotationSwotTable 


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
<td><p>Creates one or multiple entries in the smmSWOTTable table for each record in the smmQuotationSWOTTable that is associated with a quotation, project, or campaign entry.</p></td>
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


## Remarks

The entries that are created in the smmSWOTTable table represent the strength, weakness, opportunity, and threat notes in separate records.

  


