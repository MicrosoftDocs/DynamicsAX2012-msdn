---
title: ReleaseUpdateDB60_Req.updateReqSitePolicy Upgrade Script
TOCTitle: ReleaseUpdateDB60_Req.updateReqSitePolicy Upgrade Script
ms:assetid: aa69d8a0-8318-0f1d-bcd0-016f85e84177
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686440(v=AX.60)
ms:contentKeyID: 49710396
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Req.updateReqSitePolicy Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Req</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateReqSitePolicy</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates the default records in the ReqSitePolicy table.</p></td>
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
<td><p>Master planning</p></td>
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
<td><p>ReqSitePolicy</p></td>
</tr>
</tbody>
</table>


## Remarks

For each site, the record is created in the ReqSitePolicy table with the value of the UseTransferJournals field set to false.

  


