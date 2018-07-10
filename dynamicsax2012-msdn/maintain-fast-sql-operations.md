---
title: Maintain Fast SQL Operations
TOCTitle: Maintain Fast SQL Operations
ms:assetid: a32f772e-c1d3-48ff-9553-eb1657b51d23
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa849875(v=AX.60)
ms:contentKeyID: 35248363
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Maintain Fast SQL Operations 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

There are situations where X++ SQL record set operations can be converted to slower record-by-record operations.

The following table identifies these situations.

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p></p></th>
<th><p><a href="delete-from.md">DELETE_FROM</a></p></th>
<th><p><a href="update-recordset.md">UPDATE_RECORDSET</a></p></th>
<th><p><a href="insert-recordset.md">INSERT_RECORDSET</a></p></th>
<th><p><a href="optimizing-record-inserts.md">ARRAY_INSERT</a></p></th>
<th><p>Use ... to override</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Non-SQL tables</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Not applicable</p></td>
</tr>
<tr class="even">
<td><p>Delete actions</p></td>
<td><p>Yes</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>skipDeleteActions</p></td>
</tr>
<tr class="odd">
<td><p>Database log enabled</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>No</p></td>
<td><p>skipDatabaseLog</p></td>
</tr>
<tr class="even">
<td><p>Overridden method</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>skipDataMethods</p></td>
</tr>
<tr class="odd">
<td><p>Alerts set up for table</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>No</p></td>
<td><p>skipEvents</p></td>
</tr>
<tr class="even">
<td><p><strong>ValidTimeStateFieldType</strong> property not equal to <strong>None</strong> on a table</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Not applicable</p></td>
</tr>
</tbody>
</table>

 

You may explicitly skip or ignore one or more things that would adversely impact performance by using the items shown in the far right column. If for some reason one of the previously mentioned SQL operations is downgraded to a record-by-record operation, all of the skip… settings are also ignored. For example, the insert method on myTable is executed in the following example—even though it is explicitly stated that this method should be skipped if myTable has a container or memo field defined.
```X++
    public void tutorialRecordInsertList()
    {
        MyTable myTable;
        RecordInsertList insertList = new RecordInsertList(
            myTable.TableId, 
            True);
        int i;
        
        for ( i = 1; i <=  100; i++ )
        {
            myTable.value = i;
            insertList.add(myTable);
        }
        insertList.insertDatabase();
    }
```
 

For more information about delete actions, see [Maintaining Data Integrity](maintaining-data-integrity.md).

## See also

[Speeding Up SQL Operations](speeding-up-sql-operations.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

