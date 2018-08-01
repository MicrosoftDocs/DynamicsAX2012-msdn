---
title: ReleaseUpdateTransformDB40_Basic.updateAddressCityPreProcessing_BR Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Basic.updateAddressCityPreProcessing_BR Upgrade Script
ms:assetid: 64328f43-6a1d-639d-a2ff-3136de26ba68
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719169(v=AX.60)
ms:contentKeyID: 49708708
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Basic.updateAddressCityPreProcessing\_BR Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateAddressCityPreProcessing_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This script is used for updating the Brazilian address city data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p>
<p>Pre-processing60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
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
<td><p>DEL_AddressCityTableUpgrade_BR</p></td>
</tr>
</tbody>
</table>


## Remarks

The script creates new \<c\>DEL\_AddressCityTableUpgrade\_BR\</c\> records to support city upgrade.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: AddressCityTable_BR</p></th>
<th><p>To Table: DEL_AddressCityTableUpgrade_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>recVersion</p></td>
<td><p>RecVersionId</p></td>
</tr>
<tr class="odd">
<td><p>CountryId</p></td>
<td><p>OldCountryRegionId</p></td>
</tr>
<tr class="even">
<td><p>StateId</p></td>
<td><p>OldStateId</p></td>
</tr>
<tr class="odd">
<td><p>dataAreaId</p></td>
<td><p>OldDataAreaId</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_AddressCountryRegionUpgrade</p></th>
<th><p>To Table: DEL_AddressCityTableUpgrade_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NewCountryRegionId</p></td>
<td><p>NewCountryRegionId</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_AddressStateUpgrade</p></th>
<th><p>To Table: DEL_AddressCityTableUpgrade_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NewStateId</p></td>
<td><p>NewSateId</p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AddressCityTable_BR</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


