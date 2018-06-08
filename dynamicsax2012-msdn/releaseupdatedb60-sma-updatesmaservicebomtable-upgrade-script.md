---
title: ReleaseUpdateDB60_SMA.updateSMAServiceBOMTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_SMA.updateSMAServiceBOMTable Upgrade Script
ms:assetid: 493a6fd0-b338-bd87-f0d7-18e3da2fe6b2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685348(v=AX.60)
ms:contentKeyID: 49708032
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_SMA.updateSMAServiceBOMTable Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_SMA</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateSMAServiceBOMTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>The method updates all records from the SMAServiceBOMTable table where the itemType field equals to the DEL_BOM value.</p></td>
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
<td><p>Service</p></td>
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
<td><p>SMAServiceBOMTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This is part of removal of the BOM item type. All items with the DEL\_BOM value on the ItemType field should receive the Item value.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

