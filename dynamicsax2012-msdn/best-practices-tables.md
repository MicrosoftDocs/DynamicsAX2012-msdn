---
title: 'Best Practices: Tables'
TOCTitle: 'Best Practices: Tables'
ms:assetid: dbcb7500-c393-46da-909f-1dd1c0d4378d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa876262(v=AX.60)
ms:contentKeyID: 35252076
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices: Tables [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This section of the SDK describes the best practices for tables.

## Best Practice Checks

The following table lists the best practices error messages and how to fix the errors.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Message</p></th>
<th><p>Message type</p></th>
<th><p>How to fix the error or warning</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Table %1 with SysDeletedObjects configuration key (%2) has no DEL_prefix.</p></td>
<td><p>Error</p></td>
<td><p>The object is linked to a SysDeletedObjects configuration key but is not marked as DEL_. Mark the object as DEL_.</p></td>
</tr>
<tr class="even">
<td><p>Table %1 with DEL_prefix has configuration %2 instead of SysDeletedObjects.</p></td>
<td><p>Error</p></td>
<td><p>The object is marked as DEL_ but it is not linked to a SysDeletedObjects configuration key. Unmark the object as DEL_ or link to the SysDeletedObjects configuration key.</p></td>
</tr>
<tr class="odd">
<td><p>Index %1 with SysDeletedObjects configuration key (%2) has no DEL_prefix.</p></td>
<td><p>Error</p></td>
<td><p>The object is linked to a SysDeletedObjects configuration key but is not marked as DEL_. Mark the object as DEL_.</p></td>
</tr>
<tr class="even">
<td><p>Field %1 with DEL_ prefix has configuration %2 instead of SysDeletedObjects.</p></td>
<td><p>Error</p></td>
<td><p>The object is marked as DEL_ but it is not linked to a SysDeletedObjects configuration key. Link to the SysDeletedObjects configuration key.</p></td>
</tr>
<tr class="odd">
<td><p>Field %1 with SysDeletedObjects configuration key (%2) has no DEL_ prefix.</p></td>
<td><p>Error</p></td>
<td><p>The object is linked to a SysDeletedObjects configuration key but is not marked as DEL_. Mark the object as DEL_.</p></td>
</tr>
<tr class="even">
<td><p>RecID field cannot be part of the NaturalKey index.</p></td>
<td><p>Error</p></td>
<td><p>A RecID field was set as the replacement key.</p>
<p>Best practice rule that supports relational application design.</p>
<p>This best practice check requires an exclusive RecID in the inheritance hierarchy. When you create a new field in a table, the best practice logic iterates through the inheritance hierarchy to ensure the RecID and ReplacementKey indexes are exclusive.</p></td>
</tr>
<tr class="odd">
<td><p>Table is using CreatedDateTime or ModifiedDateTime, RecId index needs to be created.</p></td>
<td><p>Error</p></td>
<td><p>When a table has a CreatedDateTime or ModifiedDateTime field, it must have a RecID index.</p></td>
</tr>
</tbody>
</table>


## In This Section

Additional best practice errors relating to tables are described in the following topics.

  - [Best Practices for Table Properties](best-practices-for-table-properties.md)  

  - [Best Practices: Table Fields](best-practices-table-fields.md)  

  - [Best Practices for Indexes](best-practices-for-indexes.md)  

  - [Best Practices for Table Relations](best-practices-for-table-relations.md)  

  - [Best Practices for Table Methods](best-practices-for-table-methods.md)  

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

