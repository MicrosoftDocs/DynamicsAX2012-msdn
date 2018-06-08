---
title: ReleaseUpdateDB41_Prod.updateWrkCtrParametersDim Upgrade Script
TOCTitle: ReleaseUpdateDB41_Prod.updateWrkCtrParametersDim Upgrade Script
ms:assetid: c5b58775-5a8d-5da4-c6b6-abb47b52d662
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719540(v=AX.60)
ms:contentKeyID: 49711108
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Prod.updateWrkCtrParametersDim Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_Prod</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateWrkCtrParametersDim</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the WrkCtrParametersDim table from the WrkCtrParameters table.</p></td>
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
<td><p>Production</p></td>
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
<td><p>WrkCtrParametersDim</p></td>
</tr>
</tbody>
</table>


## Remarks

The WrkCtrParametersDim.del\_LimitCapProdPOM and WrkCtrParametersDim.del\_LimitCapProdProject fields are updated with the values of the corresponding fields in the WrkCtrParameters table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

