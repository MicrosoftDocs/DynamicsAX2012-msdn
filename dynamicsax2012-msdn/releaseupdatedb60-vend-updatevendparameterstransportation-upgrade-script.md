---
title: ReleaseUpdateDB60_Vend.updateVendParametersTransportation Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendParametersTransportation Upgrade Script
ms:assetid: 767abb6a-448a-fcb9-2f4d-ccf8fb7bb680
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719337(v=AX.60)
ms:contentKeyID: 49709128
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendParametersTransportation Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateVendParametersTransportation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TransportationProperties_LT field in the VendParameters table to the DoPrintTransportationDocument field.</p></td>
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
<td><p>Accounts receivable</p></td>
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
<td><p>VendParameters</p></td>
</tr>
</tbody>
</table>


## Remarks

The update is handled by the upgrade framework and no upgrade script has been produced.

## Name Changes for Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Old Table Name: VendParameters</p></th>
<th><p>New Table Name: VendParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>TransportationProperties_LT</p></td>
<td><p>DoPrintTransportationDocument</p></td>
</tr>
</tbody>
</table>

  


