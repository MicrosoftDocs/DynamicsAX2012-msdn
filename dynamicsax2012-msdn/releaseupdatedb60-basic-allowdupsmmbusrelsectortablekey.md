---
title: ReleaseUpdateDB60_Basic.allowDupsmmBusRelSectorTableKey
TOCTitle: ReleaseUpdateDB60_Basic.allowDupsmmBusRelSectorTableKey
ms:assetid: a8806950-71f9-f458-1008-206cb9314867
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686393(v=AX.60)
ms:contentKeyID: 49710349
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowDupsmmBusRelSectorTableKey 


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
<td><p>allowDupsmmBusRelSectorTableKey</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Disable KeyIdx index in &lt;c&gt;smmBusRelSectorTable&lt;/c&gt;</p></td>
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
<td><p>SysInfolog</p></td>
</tr>
</tbody>
</table>


## Remarks

The index is set to allow duplicates for the key field in the smmBusRelSectorTable table.

  


