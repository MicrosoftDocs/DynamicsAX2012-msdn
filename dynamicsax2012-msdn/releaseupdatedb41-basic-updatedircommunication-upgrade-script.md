---
title: ReleaseUpdateDB41_Basic.updateDirCommunication Upgrade Script
TOCTitle: ReleaseUpdateDB41_Basic.updateDirCommunication Upgrade Script
ms:assetid: c51b8c83-58b7-d7ec-9ce8-49612c85b3cb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719509(v=AX.60)
ms:contentKeyID: 49711077
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Basic.updateDirCommunication Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateDirCommunication</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This method creates entries in the table for the Email, Phone+PhoneLocal, URL, CellularPhone, TeleFax, Pager, SMS, Telex fields that are found in HRP Employee.</p></td>
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
<td><p>DEL_DirECommunicationAddress</p></td>
</tr>
<tr class="even">
<td><p>DEL_DirECommunicationRelationship</p></td>
</tr>
</tbody>
</table>


## Remarks

The communication types exist in the DEL\_DirCommunicationType table. That assumes the smmDataPopulation.insertDirCommunicationType method has been called.

  


