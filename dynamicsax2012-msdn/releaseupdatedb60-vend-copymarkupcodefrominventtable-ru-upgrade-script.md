---
title: ReleaseUpdateDB60_Vend.copyMarkupCodeFromInventTable_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.copyMarkupCodeFromInventTable_RU Upgrade Script
ms:assetid: 6adaa831-4993-ba90-f7c5-73a0f9f1d4f5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685683(v=AX.60)
ms:contentKeyID: 49708884
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.copyMarkupCodeFromInventTable\_RU Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>copyMarkupCodeFromInventTable_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the PurchLine table.</p></td>
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
<td><p>PurchLine</p></td>
</tr>
</tbody>
</table>


## Remarks

Updating all purchase lines linked to Inventory table which meet the following condition: - Type is Service; - MarkupCode\_RU is not empty.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

