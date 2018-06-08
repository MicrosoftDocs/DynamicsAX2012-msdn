---
title: Optimizing Record Inserts
TOCTitle: Optimizing Record Inserts
ms:assetid: e22808da-c623-4b23-884c-ddf5fa1be66d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa879372(v=AX.60)
ms:contentKeyID: 35253101
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Optimizing Record Inserts 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Array inserts, sometimes referred to as bulk inserts, are implemented in the kernel. They buffer a group of rows and insert them in a single trip to the SQL data store. This vastly reduces the number of trips, and speeds up inserts by approximately a factor of 2 – 10. You can use [RecordSortedList](https://msdn.microsoft.com/en-us/library/gg923766\(v=ax.60\)) or [RecordInsertList](https://msdn.microsoft.com/en-us/library/gg923748\(v=ax.60\)) to hold your rows until they are inserted. Both classes have an insertDatabase method that is used to insert the records into the database as efficiently as possible. However, the insertDatabase method does not empty the list itself.

Array inserts can [fall back to record-by-record operations](maintain-fast-sql-operations.md) in a number of situations.

You can also use [insert\_recordset](insert-recordset.md) to insert multiple rows on a single server trip. It is faster than an array insert, but limited to simple manipulations that can be implemented as SQL expressions. Array inserts enable you to perform more manipulation on the data before it is inserted.

## Example 1

    RecordSortedList rsl;
    MyTable          myTable;
    ;
    rsl = new RecordSortedList(myTable.tableid);
    rsl.sortOrder(fieldname2id(myTable.tableId,'RecId'));
    myTable.field1 = 'Value1';
    rsl.ins(myTable);
    myTable.field1 = 'Value2';
    rsl.ins(myTable);
    rsl.insertDatabase();

Two records, Value1 and Value2, are inserted into myTable. The values are inserted in sorted order before finally being inserted into the database.

## Example 2

    void tutorialRecordSortedList()
    {
        RecordSortedList recordSortedList;
        CustTable        custTable;
        ;
        recordSortedList = new RecordSortedList(tablenum(CustTable));
        recordSortedList.sortOrder(fieldnum(CustTable,AccountNum));
     
        ttsBegin;
            // Prepare record #1 for insertion
            custTable.AccountNum = '1000';     
            custTable.CreditMax = 10000.0;
            recordSortedList.ins(custTable);
     
            // Prepare record #2 for insertion
            custTable.AccountNum = '2000';     
            custTable.CreditMax = 500.0;
            recordSortedList.ins(custTable);
     
            // Prepare record #N for insertion
            custTable.AccountNum = 'N000';     
            custTable.CreditMax = 9999999.9;
            recordSortedList.ins(custTable);
     
            // All records inserted in 1 database operation
            recordSortedList.insertDatabase(); 
        ttsCommit;
    }
    void tutorialRecordInsertList()
    {
        MyTable myTable;
        RecordInsertList insertList = new RecordInsertList(myTable.TableId);
        int recordsCurrentlyInserted, i, recordsToInsert = 125;
        ;
        for (i = 1; i <= recordsToInsert; i++)
        {
            myTable.value = i;
            recordsCurrentlyInserted = insertList.add(myTable);
            info(strfmt("%1 records added, %2 records currently inserted.",
                 i,recordsCurrentlyInserted));
        }
        recordsCurrentlyInserted = insertList.insertDatabase();
        info(strfmt("%1 records added, %2 records currently inserted.",
            recordsToInsert,recordsCurrentlyInserted));
    }

## See also

[How to: Update Data](how-to-update-data.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

