---
title: ReleaseUpdateDB41_smm.updateSmmOpportunity
TOCTitle: ReleaseUpdateDB41_smm.updateSmmOpportunity
ms:assetid: 8ed1e443-bfd0-8157-a0f7-1f5dff2d5182
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736518(v=AX.60)
ms:contentKeyID: 49709707
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_smm.updateSmmOpportunity 


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
<td><p>updateSmmOpportunity</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>For each master quotation that is associated with a BusRel entry, create an opporunity and link it to the PartyId of the BusRel. For any linked quotations, associate them with the same opportunity for the master quotation.</p></td>
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
<td><p>CustTable</p></td>
</tr>
<tr class="even">
<td><p>HierarchyLinkTable</p></td>
</tr>
<tr class="odd">
<td><p>HierarchyTreeTable</p></td>
</tr>
<tr class="even">
<td><p>SalesQuotationTable</p></td>
</tr>
<tr class="odd">
<td><p>smmActivityParentLinkTable</p></td>
</tr>
<tr class="even">
<td><p>smmBusRelTable</p></td>
</tr>
<tr class="odd">
<td><p>smmOpportunityTable</p></td>
</tr>
<tr class="even">
<td><p>smmProcessStage</p></td>
</tr>
<tr class="odd">
<td><p>smmQuotationAlternativeQuotations</p></td>
</tr>
</tbody>
</table>


## Remarks

For each master quotation that is associated with a BusRel entry, create an opporunity and link it to the PartyId of the BusRel. For any linked quotations, associate them with the same opportunity for the master quotation.

  


