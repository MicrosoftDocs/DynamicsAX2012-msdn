---
title: ReleaseUpdateDB60_Invent.createWMSLocationLoadCurrentPallets Upgrade Script
TOCTitle: ReleaseUpdateDB60_Invent.createWMSLocationLoadCurrentPallets Upgrade Script
ms:assetid: 2d52c6d2-b9c5-d22e-5bfa-ae12d3159fdc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735995(v=AX.60)
ms:contentKeyID: 49707412
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.createWMSLocationLoadCurrentPallets Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Invent</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>createWMSLocationLoadCurrentPallets</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates WMSLocationLoad records that contain aggregated physical values for the WMSLocation table. The records are created based on pallets in the location.</p></td>
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
<td><p>Inventory management</p></td>
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
<td><p>WMSLocation</p></td>
</tr>
<tr class="even">
<td><p>WMSPallet</p></td>
</tr>
<tr class="odd">
<td><p>WMSPalletType</p></td>
</tr>
<tr class="even">
<td><p>WMSLocationLoad</p></td>
</tr>
<tr class="odd">
<td><p>SysLastValue</p></td>
</tr>
</tbody>
</table>

  


