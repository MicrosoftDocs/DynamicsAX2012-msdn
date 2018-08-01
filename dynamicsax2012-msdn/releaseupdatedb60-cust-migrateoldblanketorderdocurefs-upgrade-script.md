---
title: ReleaseUpdateDB60_Cust.migrateOldBlanketOrderDocuRefs Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.migrateOldBlanketOrderDocuRefs Upgrade Script
ms:assetid: a9a627e6-5850-adce-1c15-9df6e2b53202
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686435(v=AX.60)
ms:contentKeyID: 49710391
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.migrateOldBlanketOrderDocuRefs Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>migrateOldBlanketOrderDocuRefs</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Re-attaches all the documents and lines that were previously attached to the sales order of Blanket type to the newly created sales agreements.</p></td>
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
<td><p>DocuRef</p></td>
</tr>
</tbody>
</table>


## Remarks

This method is called from the updateBOs2SalesAgreements method.

  


