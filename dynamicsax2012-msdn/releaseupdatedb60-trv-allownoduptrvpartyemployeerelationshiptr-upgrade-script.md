---
title: ReleaseUpdateDB60_Trv.allowNoDupTrvPartyEmployeeRelationshipTr Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.allowNoDupTrvPartyEmployeeRelationshipTr Upgrade Script
ms:assetid: 2e5281a1-79bb-2d4e-82d9-780c4d2048b0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736009(v=AX.60)
ms:contentKeyID: 49707424
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.allowNoDupTrvPartyEmployeeRelationshipTr Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Trv</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupTrvPartyEmployeeRelationshipTr</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TrvWorkerIdx index to not allow for duplicate records.</p></td>
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
<td><p>Expense management</p></td>
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
<td><p>TrvPartyEmployeeRelationship</p></td>
</tr>
</tbody>
</table>


## Remarks

Resets the TrvWorkerIdx index to not allow for duplicate records in the Worker field.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

