---
title: ReleaseUpdateDB60_Proj.allowDupProjExpPolicyGroupEmplHcmWorkerI Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.allowDupProjExpPolicyGroupEmplHcmWorkerI Upgrade Script
ms:assetid: b453e173-8ee3-f634-e09b-a013cfb44a65
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736960(v=AX.60)
ms:contentKeyID: 49710644
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.allowDupProjExpPolicyGroupEmplHcmWorkerI Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Proj</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowDupProjExpPolicyGroupEmplHcmWorkerI</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the HcmWorkerIdx index in the ProjExpPolicyGroupEmpl table to allow for duplicate records.</p></td>
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
<td><p>Project</p></td>
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
<td><p>ProjExpPolicyGroupEmpl</p></td>
</tr>
</tbody>
</table>


## Remarks

The EmplId field is replaced with the new Worker surrogate key field and a new HcmWorkerIdx unique index has been created. Initially this field contains no value. So the index is set to allow for duplicates before the field is updated with the value of the record ID field of the HcmWorker table.

  


