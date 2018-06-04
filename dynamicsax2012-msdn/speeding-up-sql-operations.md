---
title: Speeding Up SQL Operations
TOCTitle: Speeding Up SQL Operations
ms:assetid: 704c5d17-9b6c-4073-bda1-853bd0c13d8a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa673589(v=AX.60)
ms:contentKeyID: 35244901
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Speeding Up SQL Operations 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following constructs allow you to insert, update, or delete multiple records. Using these constructs reduces communication between the application and the database, and it increases performance.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Construct</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg923766(v=ax.60)">RecordSortedList</a></p></td>
<td><p>Allows you to insert multiple records in one database trip. Use the RecordSortedList construct when you want a subset of data from a particular table, and when you want it sorted in an order that does not currently exist as an index.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg923748(v=ax.60)">RecordInsertList</a></p></td>
<td><p>Allows you to insert multiple records in one database trip. Use the RecordInsertList construct when you do not need to sort the data.</p></td>
</tr>
<tr class="odd">
<td><p><a href="insert-recordset.md">insert_recordset</a></p></td>
<td><p>Allows you to copy multiple records from one or more tables directly into another table on a single database trip.</p></td>
</tr>
<tr class="even">
<td><p><a href="update-recordset.md">update_recordset</a></p></td>
<td><p>Allows you to update multiple rows in a table on a single database trip.</p></td>
</tr>
<tr class="odd">
<td><p><a href="delete-from.md">delete_from</a></p></td>
<td><p>Allows you to delete multiple records from the database on a single database trip.</p></td>
</tr>
</tbody>
</table>


In some situations, X++ record set operations can fall back to record-by-record operations. For more information, see [Maintain Fast SQL Operations](maintain-fast-sql-operations.md).

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

