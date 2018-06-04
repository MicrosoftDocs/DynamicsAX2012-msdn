---
title: Effect of Disabling a Table or Column
TOCTitle: Effect of Disabling a Table or Column
ms:assetid: 491ffbf4-54a3-4293-9de7-40dd689da286
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg845255(v=AX.60)
ms:contentKeyID: 35243143
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Effect of Disabling a Table or Column 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Starting in Microsoft Dynamics AX 2012, the column in the underlying database table is not dropped when its corresponding field is disabled in the AOT. Also, an underlying table is not dropped when its corresponding table is disabled in the AOT. Instead, the system treats the disabled table as a [temporary TempDB table](temporary-tempdb-tables.md). This means that any inserts of data into the table are undone and discarded when the table variable goes out of scope.

A field or table can be disabled by manipulation of a [configuration key](how-to-create-and-apply-a-configuration-key.md). When a configuration key is turned off, a set of tables becomes disabled. However, the data remains in the disabled tables. Later, if the configuration key is turned back on, the tables become reenabled and their data becomes available again.

## Additional Details

The following table describes additional details about tables and columns that are disabled by a configuration key.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Detail</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Previous behavior</p></td>
<td><p>In an earlier version of the product, Microsoft Dynamics AX 2009, the disabled column or table was dropped from the underlying database. This had the drawback of breaking any <a href="https://msdn.microsoft.com/en-us/library/cc615265(v=ax.60)">cubes</a> or reports in the AOT that referenced the disabled column or table.</p>
<p>Also, any external software that read the disabled column directly from the database was also broken. Reports that are written directly in SQL Server Reporting Services (SSRS) as a named query are an example.</p>
<p>Regarding disabled tables and columns, the current behavior of Microsoft Dynamics AX is the same as in Microsoft Dynamics AX 2009 for everything in the AX32.exe or MorphX client. For instance, even though the underlying column is not dropped when a field is disabled, an X++ SQL select statement still does not return the disabled field.</p></td>
</tr>
<tr class="even">
<td><p>Decide whether to delete data</p></td>
<td><p>The administrator who disables a table or field must decide either to leave the data in the underlying database table or column, or to manually delete the data. The decision does not affect AOT items like cubes and reports, but it could affect external software that reads the underlying table directly.</p></td>
</tr>
<tr class="odd">
<td><p>Disabled field on a table</p></td>
<td><p>A query that selects a disabled field does not receive that field in the results set. The field is filtered out of the results by the system.</p></td>
</tr>
<tr class="even">
<td><p>Unique index</p></td>
<td><p>If a column becomes disabled when it is part of a two column unique index, the uniqueness of the values is no longer guaranteed. To prevent uniqueness violations, the developer or administrator should modify the index in the AOT.</p></td>
</tr>
</tbody>
</table>


## See also

[Temporary InMemory Tables](temporary-inmemory-tables.md)

[How to: Create and Apply a Configuration Key](how-to-create-and-apply-a-configuration-key.md)

[Using the MorphX Security System](using-the-morphx-security-system.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

