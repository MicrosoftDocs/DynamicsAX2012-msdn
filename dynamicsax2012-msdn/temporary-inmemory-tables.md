---
title: Temporary InMemory Tables
TOCTitle: Temporary InMemory Tables
ms:assetid: 6875e6be-81c7-47fb-9534-42f59859e8af
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb314749(v=AX.60)
ms:contentKeyID: 35244759
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Temporary InMemory Tables [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, one type of temporary table is the InMemory table. We call them InMemory tables because their **TableType** property value is **InMemory**. This value comes from the **TableType::InMemory** enum value. The **TableType** property value can be seen at **AOT** \> **Data Dictionary** \> **Tables** \> MyInMemoryTable \> **Properties** \> **TableType**.


> [!NOTE]
> <P>In Microsoft Dynamics AX 2009 and earlier versions, InMemory tables were called temporary tables. Now there are two kinds of temporary tables, namely InMemory tables and TempDB tables. To avoid confusion we do not use the phrase temporary tables to refer to just InMemory tables or to just <A href="temporary-tempdb-tables.md">TempDB</A> tables.</P>



## Tier

InMemory tables are instantiated in the active memory of which ever tier the process is running on, either the client or the server tier. InMemory tables are never represented in the database management system.

An InMemory table is held in memory until its size reaches 128 KB. The dataset is then written to a disk file on the server tier. The disk file for an InMemory table has the naming convention $tmp\<nnnnnnnn\>.$$$.

## Scope

An InMemory table is instantiated when the first record is inserted. The instantiated InMemory table continues to exist only while a record buffer variable that references the table exists. The memory or disk space for the InMemory table is de-allocated as soon as the record buffer goes out of scope.

## Adding Data to an InMemory Table

To add data to an InMemory table, you must declare the record buffer and call the insert method. The following code example uses the TmpCustLedger table which has its **TableType** property set to **InMemory** in the AOT.

    static void TableTmpInsertRecord(Args _args)
    {
        TmpCustLedger custTmpLedger;
        ;
        custTmpLedger.Name = 'NameValue';
        custTmpLedger.Balance01 = 2345000;
        custTmpLedger.insert();
    }

To free the memory and delete the file for the InMemory table, set the record buffer variable to null as follows.

custTmpLedger = null;

The following code example copies data from the CustTable table into an InMemory table that is a copy of the CustTable table structure. The setTmp method is used to create an InMemory table that matches the CustTable table. The setTmp method changes the value that is returned from the getTableType method, from TableType::Regular to TableType::InMemory.

    static void CopyPersistedTableToInMemoryJob(Args _args)
    {
        CustTable custTable;
        CustTable custTmpLedger;
    
        custTmpLedger.setTmp();
        custTable.recordLevelSecurity(true);
    
        while select * from custTable where custTable.AccountNum like '1*'
        {
            custTmpLedger.data(custTable.data());
            custTmpLedger.doInsert();
            info(strFmt("Inserted a row for AccountNum = %1",custTable.AccountNum));
        }
    
        custTmpLedger = null;
    }

## Indexes

Indexes can be defined on an InMemory table just as you would a persisted table. If an InMemory table is created by copying a persisted table, the indexes are also copied to the InMemory table. Indexes are useful for quickly retrieving data from InMemory tables, especially if the InMemory table data is in a disk file.

## InMemory Tables vs. Containers

Microsoft Dynamics AX supports a special data type called a container. This data type can be used just as you would use an InMemory table. For more information, see [Containers](containers.md).

Data in containers are stored and retrieved sequentially, but an InMemory table enables you to define indexes to speed up data retrieval. An index is of no benefit if you are working with only a few records. In such cases a container might involve less overhead and perform faster than an InMemory table.

Another important difference between InMemory tables and containers is how they are used in method calls. When you pass an InMemory table into a method call, it is passed by reference. Containers are passed by value. When a variable is passed by reference, only a pointer to the object is passed into the method. When a variable is passed by value, a new copy of the variable is passed into the method. If the computer has a limited amount of memory, it might start swapping memory to disk, slowing down application execution. When you pass a variable into a method, an InMemory table may provide better performance than a container.

For more information about temporary tables, see Greef, Pontoppidan, et al. 2006. *Inside Microsoft Dynamics AX 4.0*. 351-359. Redmond: Microsoft Press.

## TempDB Tables for Disabled Tables

You can disable a regular persisted database table by disabling the [configuration key](how-to-create-and-apply-a-configuration-key.md) that controls the table. Disabling the key causes the system to automatically create a TempDB style of temporary table that matches the fields and schema of the database table. This temporary table exists in the underlying SQL Server database and is managed by the Application Object Server (AOS).

The purpose of automatically creating this TempDB table is to enable AOT objects that reference the disabled table to continue to compile and run. You can read and write to this TempDB table even though the configuration key is disabled.

All table buffer variables inherit the methods of the xRecord class. One such method is setTmp, which creates an InMemory temporary table that has the same schema as the regular table. However, the setTmp method cannot create an InMemory table from a TempDB table. You can call the method isTempDb to determine whether the setTmp method is available.

## See also

[Use the Table Browser to View, Add, Modify, or Delete Records](use-the-table-browser-to-view-add-modify-or-delete-records.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

