---
title: ReleaseUpdateDB60_Vend.migrateOldBlanketOrderDocuRefs Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.migrateOldBlanketOrderDocuRefs Upgrade Script
ms:assetid: 7ab3e96e-bb39-7ccd-21fb-f07fe1b65589
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719422(v=AX.60)
ms:contentKeyID: 49709213
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.migrateOldBlanketOrderDocuRefs Upgrade Script [AX 2012]


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
<td><p>migrateOldBlanketOrderDocuRefs</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Re-attaches all the documents that are previously attached to the sales order of type Blanket and all its lines to the newly created sales agreements.</p></td>
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
<td><p>Accounts payable</p></td>
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
<td><p>DocuRef</p></td>
</tr>
</tbody>
</table>


## Remarks

Called from the updateBOs2PurchAgreements method.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

