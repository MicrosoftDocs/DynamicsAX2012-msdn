---
title: Server/Client Location of Methods
TOCTitle: Server/Client Location of Methods
ms:assetid: fb205120-dd6d-4c97-b90a-f6be9c37f943
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa891949(v=AX.60)
ms:contentKeyID: 35254194
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Server/Client Location of Methods 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The table below describes what the default client/server location is for different kinds of methods, and whether this default behavior can be changed.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p></p></th>
<th><p>Default behavior</p></th>
<th><p>Can be changed</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Class Static Methods</p></td>
<td><p>Run in the same location as that designated by the RunOn property for the class.</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Class Instance Methods</p></td>
<td><p>Run in the same location as the class object. The location of instances of the class is determined by the RunOn property for the class.</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Table Static Methods</p></td>
<td><p>Run where they are called from (RunOn property is Called from).</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Table Instance Methods</p></td>
<td><p>Run where they are called from (RunOn property is Called from).</p>
<p>The standard table methods insert, doInsert, update, doUpdate, delete, and doDelete on the Server (where the data source is). This cannot be changed.</p></td>
<td><p>Yes</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

