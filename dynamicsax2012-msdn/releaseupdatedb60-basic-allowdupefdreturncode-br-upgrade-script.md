---
title: ReleaseUpdateDB60_Basic.allowDupEFDReturnCode_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowDupEFDReturnCode_BR Upgrade Script
ms:assetid: 2d4ab8f5-2bea-189b-efb5-b52bb4f178e9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735987(v=AX.60)
ms:contentKeyID: 49707404
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowDupEFDReturnCode\_BR Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>allowDupEFDReturnCode_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Disables the message type index in electronic fiscal document return codes table.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>EFDReturnCode_BR</p></td>
</tr>
</tbody>
</table>


## Remarks

This index is temporarily disabled because the EFDReturnCode\_BR table now has property save data per company "no".

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

