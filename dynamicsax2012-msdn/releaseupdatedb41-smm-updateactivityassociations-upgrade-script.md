---
title: ReleaseUpdateDB41_smm.updateActivityAssociations Upgrade Script
TOCTitle: ReleaseUpdateDB41_smm.updateActivityAssociations Upgrade Script
ms:assetid: cbba13b3-adfc-25bf-2579-228739af330c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719675(v=AX.60)
ms:contentKeyID: 49711242
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_smm.updateActivityAssociations Upgrade Script 


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
<td><p>updateActivityAssociations</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the projActivity table for the smmActivities table that is associated to the project.</p></td>
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
<td><p>ContactPerson</p></td>
</tr>
<tr class="even">
<td><p>ProjActivity</p></td>
</tr>
<tr class="odd">
<td><p>ProjTable</p></td>
</tr>
<tr class="even">
<td><p>SalesQuotationTable</p></td>
</tr>
<tr class="odd">
<td><p>SalesTable</p></td>
</tr>
<tr class="even">
<td><p>SMAServiceOrderTable</p></td>
</tr>
<tr class="odd">
<td><p>smmActivities</p></td>
</tr>
<tr class="even">
<td><p>smmActivityParentLinkTable</p></td>
</tr>
<tr class="odd">
<td><p>smmBusRelTable</p></td>
</tr>
<tr class="even">
<td><p>smmCampaignSelection</p></td>
</tr>
<tr class="odd">
<td><p>smmCampaignTable</p></td>
</tr>
<tr class="even">
<td><p>smmTMCallListGroup</p></td>
</tr>
<tr class="odd">
<td><p>smmTMCallListTable</p></td>
</tr>
</tbody>
</table>


## Remarks

Association fields in the smmActivities table have been marked for deletion and the association link has been moved out to the new smmActivityParentLinkTable table.

  


