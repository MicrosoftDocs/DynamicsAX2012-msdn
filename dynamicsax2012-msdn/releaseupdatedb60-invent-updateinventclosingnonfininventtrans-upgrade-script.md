---
title: ReleaseUpdateDB60_Invent.updateInventClosingNonFinInventTrans Upgrade Script
TOCTitle: ReleaseUpdateDB60_Invent.updateInventClosingNonFinInventTrans Upgrade Script
ms:assetid: ab4b94c7-4ba6-8c4c-87eb-f1deea9ed459
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686475(v=AX.60)
ms:contentKeyID: 49710430
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.updateInventClosingNonFinInventTrans Upgrade Script [AX 2012]


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
<td><p>updateInventClosingNonFinInventTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the InventClosingNonFinancialInventTrans table by using the DEL_NonFinancialTransfInventClosingRecId and RecId fields in the InventTrans table.</p></td>
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
<td><p>InventTrans</p></td>
</tr>
<tr class="even">
<td><p>InventParameters</p></td>
</tr>
<tr class="odd">
<td><p>InventClosingNonFinancialInventTrans</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

