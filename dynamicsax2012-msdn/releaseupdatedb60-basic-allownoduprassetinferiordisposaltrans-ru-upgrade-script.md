---
title: ReleaseUpdateDB60_Basic.allowNoDupRAssetInferiorDisposalTrans_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowNoDupRAssetInferiorDisposalTrans_RU Upgrade Script
ms:assetid: ef8c9504-121b-e839-ba86-d3c75c5b515a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737409(v=AX.60)
ms:contentKeyID: 49712104
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowNoDupRAssetInferiorDisposalTrans\_RU Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupRAssetInferiorDisposalTrans_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index AccountIdx in the table RAssetInferiorDisposalTrans not to allow duplicate records.</p></td>
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
<td><p>Fixed Asset</p></td>
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
<td><p>RAssetInferiorDisposalTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the DisposalTableRecId surrogate key field with the value of the record ID field of the RAssetInferiorDisposalTable table, the AccountIdx index is reset not to allow duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

