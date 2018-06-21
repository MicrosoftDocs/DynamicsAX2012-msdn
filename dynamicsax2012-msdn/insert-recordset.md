---
title: insert_recordset
TOCTitle: insert_recordset
ms:assetid: 34179df5-e90a-47f3-81f3-85dee6b4752f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa635694(v=AX.60)
ms:contentKeyID: 35241998
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# insert\_recordset [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

insert\_recordset copies data from one or more tables directly into one resulting destination table on a single server trip. Using insert\_recordset is faster than using an [array insert](optimizing-record-inserts.md). However, array inserts are more flexible if you want to handle the data before you insert it.

insert\_recordset is a record set-based operator, which performs operations on multiple records at a time. However, it can [fall back to record-by-record operations](maintain-fast-sql-operations.md) in many situations.

## Syntax

The ListOfFields in the destination table must match the list of fields in the source tables. Data is transferred in the order that it appears in the list of fields. Fields in the destination table that are not present in the list of fields are assigned zero-values as in other areas in X++. System fields, including RecId, are assigned transparently by the kernel in the destination table.

insert\_recordset  DestinationTable  (  ListOfFields  )

select  ListOfFields1  from  SourceTable  \[ where  WhereClause  \]

\[ join  ListOfFields2  from  JoinedSourceTable 

\[ where  JoinedWhereClause  \]\]

## Example 1: Sub-select that has a Group By

The records, myNum and mySum, are retrieved from the table anotherTable and inserted into the table myTable. The records are grouped according to myNum, and only the myNum records with a value less than or equal to 100 are included in the insertion.

    insert_recordset myTable (myNum, mySum)
        select myNum, sum(myValue) 
            from anotherTable 
            group by myNum 
            where myNum <= 100;

## Example 2: Comparing the Performance of Traditional Inserts and Insert\_recordset Inserts

By comparing the following two X++ code examples, you can see the performance implications of different designs.

### ![Aa635694.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa635694.collapse_all(en-us,AX.60).gif")Example 2a: Copy Data for Each Record

The following code example shows the traditional way of copying data.

    ttsBegin;
    while select * from sqlDictionary
        where sqlDictionary.tabId > 0
    {
        bufferDictionary.tabId        = sqlDictionary.tabId;
        bufferDictionary.fieldId      = sqlDictionary.fieldId;
        bufferDictionary.array        = sqlDictionary.array;
        bufferDictionary.name         = sqlDictionary.name;
        bufferDictionary.sqlName      = sqlDictionary.sqlName;
        bufferDictionary.fieldType    = sqlDictionary.fieldType;
        bufferDictionary.strSize      = sqlDictionary.strSize;
        bufferDictionary.shadow       = sqlDictionary.shadow;
        bufferDictionary.rightJustify = sqlDictionary.rightJustify;
        bufferDictionary.nullable     = sqlDictionary.nullable;
        bufferDictionary.flags        = sqlDictionary.flags;
        bufferDictionary.insert();
        countTables++;
        operationProgress.setCount(countTables);
    }
    ttsCommit;

### ![Aa635694.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa635694.collapse_all(en-us,AX.60).gif")Example 2b: Set Based Operation

The following code example achieves the same outcome as the previous example, but this example is much faster. This example uses the insert\_recordset statement.

    void copySQLDictionary2DictionaryLine()
    {
        SqlDictionary sqlDictionary;
        ;
     
        ttsBegin;
        insert_recordset bufferDictionary(tabId, fieldId, array, 
            name, sqlName, fieldType, strSize, shadow, 
            rightJustify, nullable, flags)
        select tabId, fieldId, array, name, sqlName, fieldType, 
            strSize, shadow, rightJustify, nullable, flags 
            from sqlDictionary
            where sqlDictionary.tabId > 0;
        ttsCommit;
    }

### ![Aa635694.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa635694.collapse_all(en-us,AX.60).gif")Performance Comparison Between 2a and 2b

When copying 14,311 rows, the number of trips to the SQL backend has been reduced from 14,213 to 6. The SQL backend time used has been reduced from 174 seconds to 10 seconds, which is a factor of 17. The overall reduction in time is larger because the new approach uses almost no resources from either the client or the Application Object Server (AOS).

## Example 3: Data Assignments from Variables

This X++ code example shows that the insert\_recordset statement can insert data that is provided in variables. In this example, the keyword firstonly is used so that only one row is inserted.


> [!NOTE]
> <P>Literals, such as 128 or "this literal string", cannot be used as a source of data to be inserted.</P>



    static void InsertVariable3Job(Args _args)
    {
        TableAlphabet    tabA2;
        BankAccountTable tabB3;
        str  1 sLetter = "a";
        str 16 sExampleWord = "apple";
        ;
        DELETE_FROM tabA2;
    
        INSERT_RECORDSET tabA2
            (Letter ,ExampleWord)
        select firstonly
            sLetter ,sExampleWord // Variables.
        from tabB3;
    
        WHILE SELECT * from tabA2
        {
            info(tabA2 .Letter + " , " + tabA2 .ExampleWord);
        }
    /***********  Actual Infolog output
    Message (04:03:52 pm)
    a , apple
    ***********/
    }

## Example 4: Joins

The following X++ code example shows a join of three tables on an insert\_recordset statement that has a sub-select. Also, a while select statement with a similar join is shown.

A variable is used to supply the inserted value for one column. The str variable must be declared with a length that is less than or equal to the maximum length of the corresponding database field.

    static void InsertJoin42Job(Args _args)
    {
        GmTabDepartment tabDept2;
        GmTabEmployee tabEmpl3;
        GmTabProject tabProj4;
        GmTabEmployeeProject tabEmplProj5;
        str 64 sDescriptionVariable = "From variable.";
        ;
        DELETE_FROM tabEmplProj5;
    
        INSERT_RECORDSET tabEmplProj5
            (
            Description
            , EmployeeRecId
            , ProjectRecId
            )
        Select
            sDescriptionVariable
            , RecId
        from
            tabEmpl3
            join
                tabDept2
                where tabEmpl3 .DepartmentGuid == tabDept2 .DepartmentGuid
            join RecId
                from tabProj4
                where tabDept2 .DepartmentGuid == tabProj4 .DepartmentGuid
        ;
    
        info(int642str(tabEmplProj5 .rowCount())
            + " ==Number of rows inserted.");
    
        WHILE SELECT *
            from
                tabEmplProj5
                join tabEmpl3
                    where tabEmplProj5 .EmployeeRecId == tabEmpl3 .RecId
                join tabProj4
                    where tabEmplProj5 .ProjectRecId == tabProj4 .RecId
        {
            info(
                tabEmpl3 .EmployeeName
                + "  --works on--  "
                + tabProj4 .ProjectName
                + " (" + tabEmplProj5 .Description + ")."
                );
        }
    /*****************  Actual Infolog output
    Message (01:05:41 pm)
    4 ==Number of rows inserted.
    Alice  --works on--  Project ZZZ (From variable.).
    Alice  --works on--  Project YY (From variable.).
    Beth  --works on--  Project ZZZ (From variable.).
    Beth  --works on--  Project YY (From variable.).
    *****************/
    }

### ![Aa635694.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa635694.collapse_all(en-us,AX.60).gif")Configuration Key Automation

The system can automatically adjust the behavior of an insert\_recordset statement that inserts into fields that have their configuration key turned off.

In the previous example (4) there is an insert\_recordset statement for tabEmplProj5. One of the target fields is named Description, and the field's data comes from the local variable sDescriptionVariable. When the configuration key for the Description field is turned off, the insert\_recordset still succeeds. The system ignores both the Description field and the variable sDescriptionVariable.

## See also

[Speeding Up SQL Operations](speeding-up-sql-operations.md)

[Maintain Fast SQL Operations](maintain-fast-sql-operations.md)

[insert Table Method](insert-table-method.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

