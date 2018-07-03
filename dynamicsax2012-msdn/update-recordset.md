---
title: update_recordset
TOCTitle: update_recordset
ms:assetid: 753d8d30-8cb7-42ce-baa2-a3ef4a59e8f7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa674382(v=AX.60)
ms:contentKeyID: 35245960
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# update\_recordset 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The X++ SQL statement update\_recordset enables you to update multiple rows in a single trip to the server. This means that certain tasks may have improved performance by using the power of the SQL server.

update\_recordset resembles [delete\_from](delete-from.md) in X++ and to UPDATE SET in SQL. It works on the database server-side on an SQL-style record set, instead of retrieving each record separately by fetching, changing, and updating.

If the update method is overridden, the implementation falls back to a classic looping construction, updating records one by one just as delete\_from does for deletions. This also means that the construction works on temporary tables, and whole-table-cached tables by using the looping construction.

## Example 1: Assigning from a Math Expression

This example updates the table myTableBuffer and increments the value in field1 by ten percent in all records in the table.
```X++
    MyTable myTableBuffer;
    ;
    update_recordset myTableBuffer
    setting field1 = field1 * 1.10;
```
## Example 2: Using a Where Clause

This example updates the table myTable in all records where field1 has the value 0. field1 is assigned the new value 1; field2 is assigned the value of the sum of fieldX and fieldY.

This example updates multiple fields at the same time, and it updates only those rows that satisfy the where clause.
```X++
    MyTable myTableBuffer;
    ;
    update_recordset myTableBuffer
    setting
        field1 = 1,
        field2 = fieldX + fieldY
    where field1 == 0;
```
## Example 3: Joining Tables in an Update

This example shows that the update\_recordset statement supports the joining of several tables. Data from the joined tables can be used to assign values to fields in the table that is being updated.
```X++
    static void Join22aJob(Args _args)
    {
        TableEmployee tabEmpl;
        TableDepartment tabDept;
        TableProject tabProj;
        ;
        update_recordset tabEmpl
        setting
            currentStatusDescription = tabDept .DeptName
                + ", " + tabProj .ProjName
        join tabDept
            where tabDept .DeptId == tabEmpl .DeptId
        join tabProj
            where tabProj .ProjId == tabEmpl .ProjId;
    
        info(strFmt("Number of records updated is %1."
            ,tabEmpl .rowCount()));
    }
```
## See also

[Speeding Up SQL Operations](speeding-up-sql-operations.md)

[Maintain Fast SQL Operations](maintain-fast-sql-operations.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

