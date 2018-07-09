---
title: 'How to: Use a Full Text Index'
TOCTitle: 'How to: Use a Full Text Index'
ms:assetid: 9e677d64-619c-4da2-b8a5-a0a855231259
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg879757(v=AX.60)
ms:contentKeyID: 35248260
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use a Full Text Index 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to create a query that uses a full text index in Microsoft Dynamics AX. A full text index can improve the speed of queries that search for words that are embedded in string and memo fields on tables.

The QueryRange class has a rangeType method. You can direct a QueryRange object to use the full text index by passing the QueryRangeType::FullText enum value to the rangeType method.

If the value you are searching for is a two word phrase with a space between the words, the system treats the space as a Boolean OR.

X++ select statements cannot use a full text index.

## Prerequisites

The prerequisite for the present topic is as follows:

  - The code example in the present topic depends on the table and full text index that are specified in [How to: Create a Full Text Index](how-to-create-a-full-text-index.md). You can understand the code example without creating the table and full text index. But if you want to run the code example, you must first create the table and full text index.

## Query Code Example that Uses a Full Text Index

The following X++ code example uses a full text index that exists on a table and field that it queries.


> [!NOTE]
> <P>The code line that mentions QueryRangeType::FullText is what makes this example use the full text index.</P>



```X++
    static void GmFTIndexQueryJob6(Args _args)
    {
        FtiTable recFtiTable; // Specified in the prerequisite topic.
    
        Query query2;
        QueryBuildDataSource queryBDSource3;
        QueryBuildRange queryBRange4;
        QueryRun queryRun5;
    
        print "Start the job.";
    
        // Ensure the proper test data is in the table.
        delete_from recFtiTable;
        recFtiTable.Field1 = "Shine on you crazy diamond.";
        recFtiTable.Field2 = "Record 1.";
        recFtiTable.insert();
        recFtiTable.Field1 = "And if there is no room upon the hill.";
        recFtiTable.Field2 = "Record 2.";
        recFtiTable.insert();
    
        // Construct and run a query that uses
        // the QueryRangeType::FullText enum value.
        query2 = new Query();
        queryBDSource3 = query2.addDataSource(tableNum(FtiTable));
        queryBRange4 = queryBDSource3.addRange(fieldNum(FtiTable, Field1));
    
        queryBRange4.rangeType(QueryRangeType::FullText);
    
        // The space character is treated as a Boolean OR.
        queryBRange4.value("diamond unfounded");
    
        // Loop through the records that are returned by the query.
        queryRun5 = new QueryRun(query2);
        while (queryRun5.next())
        {
            recFtiTable = queryRun5.get(tableNum(FtiTable));
            print "--------";
            print "Field1 == " + recFtiTable.Field1;
            print "Field2 == " + recFtiTable.Field2;
        }
        print "End the job.";
        pause;
    }
```

## See also

[Full Text Index Overview](full-text-index-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

